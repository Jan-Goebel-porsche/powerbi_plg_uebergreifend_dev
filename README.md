# PLG Übergreifend — Power BI DEV

## Purpose

This repository is the development source repository for the cross-functional
PLG Power BI reporting solution. It is prepared to receive the complete existing
Power BI Project (PBIP); no semantic model, report, or business data is generated
by this skeleton.

## Repository structure

```text
/
├── powerbi/
│   └── README.md
├── docs/
│   ├── architecture.md
│   ├── development.md
│   └── changelog.md
├── scripts/
│   └── README.md
├── .gitignore
└── README.md
```

## Development workflow

1. Clone the repository locally.
2. Copy the existing PBIP project into `powerbi/`, preserving its relative paths,
   or open its `.pbip` file if already present.
3. Open the repository root in Visual Studio Code.
4. Develop or repair artifacts using Power BI Desktop and VS Code.
5. Review changed PBIP, PBIR, and TMDL files for intended changes and sensitive data.
6. Commit with meaningful messages describing the change.
7. Push changes using feature branches where appropriate.
8. Use pull requests for review and controlled integration.

See [development guidance](docs/development.md) for validation and safe editing.

## Power BI Desktop

Use an up-to-date Power BI Desktop version supporting the project's formats.
Open the `.pbip` entry point, configure authorized DEV connections locally, and
use Desktop to validate the model and report before committing.

## PBIP / PBIR

PBIP stores project references alongside `.Report` and `.SemanticModel` folders.
PBIR provides source-controlled report definitions. Keep project references and
relative folder paths intact. The actual files will come from the existing project;
this repository does not create or convert them.

## Semantic model

The real `.SemanticModel` folder may contain TMDL definitions, DAX measures,
relationships, and date tables. Track these definitions as source, preserving
existing business logic. Do not commit local model caches or confidential data.

## Report definition

The real `.Report` folder may contain PBIR JSON, report pages, visual definitions,
and report resources. Version-control the files needed to reconstruct the report;
review changes for broken references and unintended visual or filter changes.

## VS Code development

Use VS Code to inspect source, review Git diffs, and maintain documentation.
GitHub Copilot may assist with PBIP structure analysis, PBIR JSON analysis and
repair, TMDL analysis and repair, DAX creation and validation, semantic model
documentation, relationship analysis, report documentation, and consistency checks.
Copilot must preserve existing business logic unless explicitly instructed to
change it. Review its suggestions and validate them in Power BI Desktop; never
provide secrets or confidential production data as context.

## Git workflow

Keep commits small and reviewable. Use feature branches and pull requests for
controlled integration into the DEV branch. Review both staged changes and
untracked files before committing. The `.gitignore` excludes local state, not the
PBIP/PBIR/TMDL source needed to reconstruct the project.

## Deployment / environment separation

Source integration here is not a production deployment. Promote reviewed versions
through a separately controlled release process, with environment-specific
connections and configuration supplied securely rather than hard-coded.
No deployment automation or workspace mapping is configured yet.

## DEV / TEST / PROD

- **DEV:** changes are developed and version-controlled in this repository.
- **TEST:** remains logically separated for validation before release.
- **PROD:** remains logically separated for approved production releases.

Never commit passwords, API keys, access tokens, personal access tokens, connection
secrets, credentials, or confidential production data. Environment-specific or
sensitive configuration must not be hard-coded, including inside PBIP definitions.
Use approved secure configuration and credential management outside Git.

## Documentation

- [Power BI source placement](powerbi/README.md)
- [Architecture and environment boundaries](docs/architecture.md)
- [Development and validation](docs/development.md)
- [Changelog](docs/changelog.md)
- [Scripts policy](scripts/README.md)
