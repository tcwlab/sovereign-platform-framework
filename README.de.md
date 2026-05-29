# Sovereign Platform Framework

> Ein offenes Framework für den Aufbau souveräner Plattformen — Self-Assessment und Templates für Plattform-Teams in DACH-affinen, regulierten und mittelständischen Organisationen.

**Status:** Skelett (Version 0.1, Mai 2026). Begleitendes Werkzeug zu Band 4 der *Architecture Line* — *„Der souveräne Plattform-Bau"*.

## Wozu dieses Framework?

Eine souveräne Plattform entsteht nicht durch eine einzelne Entscheidung, sondern durch eine Folge von Stufen, auf denen Org und Architektur zusammenwachsen. Dieses Framework liefert die operative Seite dieser Reise — die theoretische Seite steht im Buch.

Konkret findest du hier:

- **Self-Assessment** — fünf Stufen-Diagnosen, in welcher du dich erkennst (Erkennen, Erproben, Einführen, Skalieren, Verankern). Pro Stufe konkrete Marker, an denen du dich selbst einordnen kannst.
- **Templates** — Org-konstitutionelle Dokumente, die du anpasst und in deine Org einführst: eine Inner-Source-Charta für Zusammen­arbeit an Code, ein Architektur-Manifest für gemeinsame Architektur-Entscheidungen.

Beides ist Werkzeug, nicht Rezept. Das Framework ersetzt nicht die Entscheidungen, die deine Org treffen muss — es macht sie sichtbar.

## Aufbau

```
sovereign-platform-framework/
├── README.de.md                 ← du bist hier
├── README.md                    ← englische Kurzfassung
├── LICENSE                      ← MIT
├── CHANGELOG.md
│
├── assessment/                  ← Self-Assessment pro Stufe
│   ├── README.md
│   ├── stage-1-erkennen.md
│   ├── stage-2-erproben.md
│   ├── stage-3-einfuehren.md
│   ├── stage-4-skalieren.md
│   ├── stage-5-verankern.md
│   └── axes-reference.md        ← die fünf Souveränitäts-Achsen
│
├── templates/                   ← Org-konstitutionelle Templates
│   ├── inner-source-charta/     ← Wie zusammenarbeiten?
│   └── architectural-manifesto/ ← Woran zusammenarbeiten?
│
└── docs/
    └── relationship-to-book.md  ← Verhältnis zum Begleit-Buch
```

## Wie nutzt du das Framework?

**Schritt 1 — Self-Assessment.** Lies die fünf Stufen-Beschreibungen unter `assessment/` und finde diejenige, in der du dich am ehesten erkennst.

**Schritt 2 — Templates anwenden.** Je nach Stufe werden bestimmte Templates relevant. Ab Stufe 3 (Einführen) sind die beiden Org-konstitutionellen Templates die wichtigsten Werkzeuge: das **Architektur-Manifest** (auf welcher Architektur ihr euch verständigt) und die **Inner-Source-Charta** (wie ihr an dieser Architektur zusammenarbeitet).

**Schritt 3 — Iterieren.** Beide Templates sind versionierte, lebende Dokumente. Sie werden in deiner Org als Pull-Request-getragene Artefakte gepflegt — die Templates leben vor, was sie fordern.

## Verhältnis zum Begleit-Buch

Dieses Framework ist die **operative** Seite. Das Buch *„Der souveräne Plattform-Bau"* (Band 4 der *Architecture Line*) ist die **didaktische** Seite. Beide sind unabhängig nutzbar:

- Wer das Buch liest, braucht das Framework nicht — die Werkzeuge sind im Buch als Kapitel/Anhang vorhanden.
- Wer das Framework nutzt, braucht das Buch nicht — die Templates und Assessments stehen für sich.
- Wer beides nutzt, hat den vollständigen Bogen: das Buch erklärt das *warum*, das Framework liefert das *wie*.

Details: [`docs/relationship-to-book.md`](docs/relationship-to-book.md).

## Lizenz und Mitarbeit

MIT-lizenziert ([`LICENSE`](LICENSE)). Beiträge sind willkommen — gerne als Pull-Request gegen `main`. Das Framework folgt Inner-Source-Prinzipien (siehe `templates/inner-source-charta/`).

## Kanonischer Ort und Sichtbarkeit

**Kanonisch:** `git.mon.k8b.co/tcwlab/sovereign-platform-framework` (Forgejo, EU-souverän gehostet). Aktuell intern; Zugang nach Einladung.

**Öffentliche Quelle:** `github.com/tcwlab/sovereign-platform-framework` (US-GitHub). Diese Spiegel-Variante ist read-only — Änderungen fließen ausschließlich aus dem kanonischen Forgejo-Pfad ein und werden im 8-Stunden-Takt plus bei jedem Commit automatisch synchronisiert.

**Mitarbeit zur Zeit.** Beiträge willkommen als **GitHub-Issue** unter [`github.com/tcwlab/sovereign-platform-framework/issues`](https://github.com/tcwlab/sovereign-platform-framework/issues). Issues werden im internen Forgejo-Pfad gesichtet und entweder eingearbeitet oder begründet abgelehnt. Bei substantiellen Beiträgen ist nach Abstimmung eine Einladung zum kanonischen Forgejo-Pfad möglich.

**Warum dieser zweistufige Aufbau.** Die Entscheidung für Forgejo-als-kanonisch ist Teil dessen, was dieses Framework lehrt — Souveränität fängt bei der Wahl der Entwicklungs-Plattform an, nicht erst beim Produkt. Der zunächst interne Modus ist eine bewusste Migrations-Schrittfolge: erst Inhalt stabilisieren, dann öffnen. Eine spätere Version dieser README wird den Wechsel auf vollständig öffentlichen Forgejo-Pfad dokumentieren.

## Quellen und Inspiration

- Hohpe, Gregor. *Cloud Strategy* (2024), *Platform Strategy* (2024), *The Software Architect Elevator* (O'Reilly 2020).
- Skelton, Matthew & Pais, Manuel. *Team Topologies* (IT Revolution 2019).
- Conway, Melvyn. *How Do Committees Invent?* Datamation, April 1968.
- InnerSource Commons — innersourcecommons.org.
- Adidas DevOps Maturity Framework — github.com/adidas/adidas-devops-maturity-framework.
- Self-Contained Systems (Tilkov et al.) — scs-architecture.org.
- The Twelve-Factor App — 12factor.net.
- CNCF Platform Engineering Maturity Model (TAG App Delivery, 2023).
- Begleit-Buch der *Architecture Line*: *„Der souveräne Plattform-Bau"* — Band 4.
