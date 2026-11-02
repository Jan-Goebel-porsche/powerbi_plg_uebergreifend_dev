# Architecture

## Scope

This repository owns the DEV source of PLG Übergreifend. The real PBIP project
will be placed under `powerbi/`. No model, report pages, measures, relationships,
data sources, or deployment topology have been defined by this skeleton.

## Project boundaries

- A `.pbip` file references the existing report and semantic model folders.
- `.Report` folders hold report definitions, including PBIR when used, pages,
  visuals, and resources.
- `.SemanticModel` folders hold semantic definitions, including TMDL when used,
  DAX, relationships, and date tables.
- Local caches and user settings are not project source.

Preserve the existing project's references, formats, and business logic. Document
actual model dependencies and report structure after importing the real project.

## Environment boundaries

DEV development and version control happen here. TEST and PROD must remain
logically separated with their own controlled configuration and release approvals.
Workspace identities, connection mappings, and promotion tooling must be documented
when agreed; they are not provisioned by this repository.

Do not hard-code environment-specific or sensitive configuration. Supply
environment configuration and credentials through approved secure mechanisms
outside Git. Never commit secrets, personal access tokens, credentials, or
confidential production data, including values embedded in queries or definitions.
