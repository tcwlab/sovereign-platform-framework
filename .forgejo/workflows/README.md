# Forgejo Workflows

CI/CD workflows for this framework. Initially minimal — only a markdown-linting workflow and a link-checking workflow. Will expand as the framework matures.

To be added:

- `lint.yml` — markdownlint against all `.md` files
- `links.yml` — broken-link detection across the framework
- `mirror.yml` — push to the GitHub discovery mirror (configured by the repo owner)

Each workflow file is added via pull request and reviewed like any Inner Source contribution.
