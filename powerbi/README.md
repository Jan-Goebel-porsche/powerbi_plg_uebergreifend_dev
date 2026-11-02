# Power BI source

Copy the existing PLG Übergreifend PBIP project into this directory, preserving
the `.pbip` entry point and the relative paths to its `.Report` and
`.SemanticModel` folders.

Track all reconstruction source, including PBIR JSON, TMDL, DAX definitions,
relationships, date tables, report pages, visuals, and required report resources
when supplied by the real project. Do not invent these artifacts or add sample
business data.

Local `.pbi` caches and settings are ignored; source files such as
`.pbi/editorSettings.json` and `.pbi/unappliedChanges.json` remain trackable.
Review the actual project's layout and `git status --ignored` after copying it.
Do not copy credentials, confidential production data, or local cache contents.

See [development guidance](../docs/development.md) before editing.
