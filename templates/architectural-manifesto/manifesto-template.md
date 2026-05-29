# Architectural Manifesto — [Organisation Name]

> **Version:** [Version] · **Effective from:** [Date] · **Review cadence:** [yearly / on major architecture event]

> *„Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure."*
> — Melvyn Conway, 1968

---

## Quality Goals

The platform serves the following quality goals. Every architecture decision is measured against these.

### Scalability

[The platform handles increasing traffic by scaling horizontally. State your scaling expectations — order of magnitude, scaling axis. Example placeholder: *„We build a robust and linearly scalable platform to ensure a stable platform proposition."*]

### Resilience

[The architecture is robust against disturbances and partial outages. As more services participate, outage probability increases; with growing business success, external attention to outages increases. State your availability target.]

### Maintainability

[The platform is easy to maintain, independent of the number of systems and services involved. Risk to manage: maintenance effort growing exponentially with the number of systems if recurrent tasks aren't automated and services are too large or complex.]

### Testability

[The platform allows easy testing of parts. State your testing-scope expectation. Example: *„It is optional to test the whole integration but required to test each Vertical/SCS."*]

### Ease of development

[New project ramp-up is short and lightweight. A loosely coupled architectural landscape makes new initiatives easier to support. Automation of testing and deployment is a goal.]

---

## Principles

The platform architecture follows these foundational principles. They are stable; only major architectural reorientation revises them.

### Vertical Boundaries

**Statement.** The platform is a modular system based on technically independent services modelled around business domains. This results in a vertical system cut called a **Vertical** or **Self-Contained System (SCS)**.

**Rationale.**

- Each Vertical is implemented as its own application with its own user interface and/or public API (also called the *contracting layer*), its own business logic, and its own data storage (called *layers*).
- Functional requirements small enough can live in a single application or service.

**Implication.**

Every Vertical is owned by exactly one team. This does not necessarily mean that only one team can change the code — the owning team has the final say on what enters the codebase, for example by merging pull requests.

**Reference.** scs-architecture.org for the canonical SCS treatment.

### Decentralization

**Statement.** There are many tools and libraries available. We define a set of tools we use; given that, we delegate decision-making and control to the teams obeying these restrictions.

**Rationale.**

- The goal is the maximisation of service autonomy.
- Making development and testing as easy as possible is strongly desired.
- Avoiding separate teams for cross-functional activities makes things faster.

**Implication.** Embracing self-service wherever possible is a wanted implication. Teams must be able to deploy software on demand.

---

## Practices

The platform follows these practices to implement the principles above.

### Hide implementation details

**Statement.** Different Verticals must not share state. Verticals hide their implementation details.

**Rationale.**

- Service implementations have to be independent of each other.
- The *(mostly) shared nothing* principle is followed.
- Technology-agnostic APIs are used to facilitate different technology stacks.

**Implication.**

- Bounded contexts followed by Verticals/SCSs must be modelled.
- Data storage must be hidden.
- HTTP sessions must not be replicated.
- Even within a SCS, there is no shared in-memory cache.
- All services are stateless.
- Services must not share database schemata, application containers, etc.

### Encapsulate Data Storage

**Statement.** For any data resource, exactly one service is responsible. This service has the sovereignty over these domain-specific data. The data supply should proceed asynchronously in the background.

**Rationale.**

- Different Verticals are only loosely coupled.
- The *„truth"* of a data record belongs to precisely one service.

**Implication.**

- Data supply is realised by two methods:
  - In the background, using asynchronous principles ([your event-streaming choice — e.g. Kafka, NATS, AMQP])
  - Via ad hoc requests strongly following REST principles (idempotency, …)
- Redundancy in data supply processes is accepted as long as data sovereignty is not undermined.
- Temporary inconsistencies between Verticals are accepted (relaxed consistency).

### Standardize Service communication

**Statement.** Communication between two Verticals is standardised in the contracting layer and, if possible, asynchronous.

**Rationale.** Many benefits: Flexibility, Easy to change, Independence of programming language, No waiting for background processes.

**Implication.**

- A REST API is only used if communication needs to be synchronous.
- Asynchronous calls are used in all other situations.

### Follow REST Principles

**Statement.** Every API of a service that cannot be implemented asynchronously follows the REST paradigm by Roy Fielding.

**Rationale.**

- REST is easy to understand.
- It is flexible to use.
- It is a standardised communication to ease integration and parallel development.

**Implication.**

- The principle leads automatically to defined resources.
- The defined HTTP verbs, status codes, and headers must be attended.
- Notice the importance of the HATEOAS principle, use of hypermedia controls.
- It enables support of HTTP caches.

### Be Scalable

**Statement.** Services (whether a whole Vertical, a layer of a Vertical, or even part of a layer) are scaled horizontally.

**Rationale.**

- Avoid scaling limits in RAM, CPU, disc, etc. — define them in the deployment manifest ([your orchestrator's deployment file — e.g. Kubernetes YAML]).
- Support multi-zone strategy ([your provider's zones — e.g. europe-west1-b, europe-west1-c, europe-west1-d]) and multi-region strategy ([your provider's regions]) if applicable.
- Prepare every SCS for elasticity (time-to-start, scaling, graceful shutdown, etc.).

**Implication.**

- All services, even within an SCS, are stateless.
- There is no stickiness in service requests.
- There must not be any kind of internal sessions.

### Isolate failure

**Statement.** Make the services as resilient as possible.

**Rationale.**

- Failures and outages will occur.
- Have a plan for failures.
- Automate error handling if it can be automated.
- Write down an Operating Instruction (OI) if it cannot be handled automatically.
- Avoid cascading failures — only loosely coupled Verticals are allowed.

**Implication.**

- Do not treat local calls like remote calls.
- Make use of timeouts and circuit breakers.

### Embrace a *„Culture of Automation"*

**Statement.** Test, deployment, and operations are entirely automated.

**Rationale.**

- The deployment time has to be very small.
- There must be stable release processes.
- Decrease the time to market.

**Implication.**

- There is only automated testing in the release process.
- Deploy the same way everywhere: locally, in DEV, and PROD, if applicable.
- If possible, use environment definitions.
- The goal is Continuous Deployment.

### Deploy independently

**Statement.** Ensure that the services can be deployed by themselves in [your CI tooling — e.g. Forgejo Actions, GitLab CI]. There is no *„manual step"* that has to be done.

**Rationale.**

- This optimises the speed of release and new features.
- It increases the autonomy of teams owning their services.

**Implication.**

- At least in the contracting layer, the API has to stay backward-compatible to allow clients (internal and external) to upgrade over time for at least one older version.
- In the Kubernetes world: We follow the one-service-per-container model; we use rolling upgrades using Kubernetes techniques.
- In the VM world: We follow the one-service-per-instance model; we use blue/green release techniques to separate deployment from release; alternatively, we use rolling upgrade techniques to roll out new versions.

### Be highly observable

**Statement.** We use semantic monitoring to see if the whole platform works correctly.

**Rationale.** Multiple instances of multiple services need central logging and monitoring. We use [your monitoring stack — e.g. Prometheus, Grafana, OpenTelemetry, Loki].

**Implication.**

- In the monitoring dashboards, joined-up views and overall services have to be built.
- Log statements have to be aggregated.
- Statistic pieces of information have to be aggregated.
- Every request processed by any Vertical has to use correlation IDs.

---

## External Standards Adopted

The manifesto adopts the following external standards rather than reinventing them.

### Twelve-Factor App

The platform follows the principles of the Twelve-Factor App (12factor.net):

| # | Factor | Statement |
|---|---|---|
| I | Codebase | One codebase tracked in revision control, many deploys |
| II | Dependencies | Explicitly declare and isolate dependencies |
| III | Config | Store config in the environment |
| IV | Backing services | Treat backing services as attached resources |
| V | Build, release, run | Strictly separate build and run stages |
| VI | Processes | Execute the app as one or more stateless processes |
| VII | Port binding | Export services via port binding |
| VIII | Concurrency | Scale out via the process model |
| IX | Disposability | Maximize robustness with fast startup and graceful shutdown |
| X | Dev/prod parity | Keep development, staging, and production as similar as possible |
| XI | Logs | Treat logs as event streams |
| XII | Admin processes | Run admin/management tasks as one-off processes |

---

## Glossary

- **Vertical / SCS** — Self-Contained System. A vertically cut, autonomously deployable, independently owned slice of the platform with its own UI, business logic, and data storage.
- **Contracting layer** — the API surface a Vertical exposes to other Verticals or external consumers.
- **OI** — Operating Instruction. A documented set of instructions to follow, for example in case of service outages.
- **HATEOAS** — Hypermedia As The Engine Of Application State. The REST principle that responses link to next available actions.
- [Add organisation-specific terms here.]

---

## Lifecycle of this manifesto

This manifesto is a living document. Changes happen via pull request against the manifesto repository. The pull request follows the same review rules as any Inner Source component (see the organisation's Inner Source Charter). Major changes — for example, adding or removing a principle — require review by [Designated body].

**Versioning.** Semantic versioning: MAJOR for principle changes, MINOR for practice additions, PATCH for clarifications.

**Cadence.** Annual review by [Designated body]. Out-of-cycle review on major architectural events (significant acquisition, regulatory shift, technology generation change).
