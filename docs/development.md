# Development

## Prerequisites

- Git, Visual Studio Code, and Power BI Desktop supporting the existing project's
  PBIP, PBIR, and TMDL formats.
- Authorized DEV access; credentials managed outside this repository.

## Workflow

1. Clone the repository locally.
2. Add the existing PBIP project under `powerbi/` with relative paths intact, or
   open the existing `.pbip` entry point in Power BI Desktop.
3. Open the repository root in VS Code.
4. Develop or repair artifacts in Desktop and VS Code, preferably on a feature
   branch. Save Desktop changes before reviewing files; avoid simultaneous edits
   to the same artifact in both tools.
5. Review changed PBIP/PBIR/TMDL files and required resources in Git. Check for
   unintended format upgrades, reference changes, business logic changes, and
   sensitive values.
6. Stage only intended files and commit with a meaningful message.
7. Push the feature branch.
8. Open a pull request for controlled DEV integration.

## Validation before review

- Inspect `git status --short`, `git diff`, and `git diff --cached` from the
  repository root. Inspect newly added files too; unstaged diffs omit untracked files.
- Use `git check-ignore -v <path>` to investigate exclusions. PBIP, PBIR JSON,
  TMDL, DAX, and required report resources must remain trackable.
- Open the project in Desktop after external edits. Check model loading,
  relationships, DAX validity, report pages, visual references, and filters.
- Where authorized, refresh against DEV sources and compare results with the
  intended existing behavior. Never use confidential production data for commits.
- Validate Copilot suggestions manually; preserve business logic unless an
  explicit requirement authorizes a change.
- Check staged source and documentation for credentials and confidential data.
  Ignore rules are a safeguard, not a secret scanner.

No automated build, lint, or test infrastructure is configured in this skeleton.
Desktop validation requires the real project and appropriate DEV access.

## Configuration and release safety

Do not commit passwords, API keys, access tokens, personal access tokens,
connection secrets, credentials, or confidential production data. Do not hard-code
environment-specific configuration in source. Use approved secure configuration
and credential management outside Git.

TEST and PROD remain logically separated from DEV. A merge here does not deploy
to either environment. Promote reviewed source only through the agreed release
process, validating environment-specific connections independently.

## Documentation maintenance

Record meaningful changes in [the changelog](changelog.md). Update
[architecture](architecture.md) when actual project structure or environment
boundaries change; avoid duplicating generated model definitions in prose.
