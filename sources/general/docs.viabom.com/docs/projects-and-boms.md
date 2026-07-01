# Source: https://docs.viabom.com/docs/projects-and-boms

# Projects & BOMs

Copy page

Organize selected parts into projects, revisions, and BOMs, then import, refine, and export your working bill of materials.

Image placeholder

Add this file to \`apps/docs/public/screenshots/\`

project-bom-workspace.png

Capture a real project view with the BOM table, revision controls, and BOM controls visible so the structure is obvious at a glance.

The docs will automatically render the real image once this file exists at /screenshots/project-bom-workspace.png.

Projects are where Via stops being just a search tool and becomes part of the real design workflow.

## [The Structure](https://docs.viabom.com/#the-structure)

Via separates a few related concepts:

- **Project**: the overall design or effort
- **Revision**: a version of that project
- **BOM**: a specific bill of materials within a revision

That split lets you keep experiments, alternates, and evolving revisions without losing the history of what changed.

## [Create A Project](https://docs.viabom.com/#create-a-project)

From the signed-in home screen, use **Create Project**. Once you are inside:

- name the project clearly
- add parts directly from search
- keep a clean revision/BOM structure as the design changes

If a project is brand new, Via can set up the initial revision and BOM for you.

## [Add Parts From Search](https://docs.viabom.com/#add-parts-from-search)

The normal loop is:

1. open the project
2. launch search inside that project
3. inspect candidates
4. add the part you want into the active BOM

Searching from inside a project matters because Via can use the active BOM and ruleset as context for later ranking.

## [Import Existing BOM Files](https://docs.viabom.com/#import-existing-bom-files)

Via supports BOM parsing for common file formats:

- `csv`
- `xlsx`
- `json`
- `yaml`

The import flow parses the file, previews the result, and lets you review the incoming changes before applying them.

Use import when you want to:

- seed a new project from an existing spreadsheet
- merge incoming changes into the active BOM
- compare parsed rows before accepting them

## [Revisions Vs BOMs](https://docs.viabom.com/#revisions-vs-boms)

Use a new revision when the design itself is advancing.

Use a new BOM inside the same revision when you want alternate sourcing, variant-specific selections, or a separate working parts list without changing the higher-level revision identity.

If you expect to compare multiple options side by side, make that split early so the history stays clear.

## [Export](https://docs.viabom.com/#export)

Export the active BOM when you need to hand it to another tool or teammate. Keep in mind that export reflects the currently selected BOM, not every BOM in the project.

## [Project Context Changes Search](https://docs.viabom.com/#project-context-changes-search)

When search runs inside a project, Via can take cues from:

- parts already in the BOM
- preferred manufacturers already in use
- active rulesets and profiles
- the broader project direction implied by existing selections

This is useful when you want continuity. If you want a fresh search, confirm you are not carrying over project context that is now too restrictive.

## [Good Working Habits](https://docs.viabom.com/#good-working-habits)

- keep BOM names specific when you are comparing alternatives
- review imports before applying them
- verify sensitive values on the part page before locking them into a BOM
- report parsing mistakes instead of silently working around them

[Part Details\\ \\ Use quick look and part details to verify extracted specs, datasheets, variants, and supply context before committing a part.](https://docs.viabom.com/docs/part-details) [Libraries\\ \\ Save preferred parts into reusable libraries so future searches can lean toward parts your team already trusts.](https://docs.viabom.com/docs/libraries)

### On this page

[The Structure](https://docs.viabom.com/#the-structure) [Create A Project](https://docs.viabom.com/#create-a-project) [Add Parts From Search](https://docs.viabom.com/#add-parts-from-search) [Import Existing BOM Files](https://docs.viabom.com/#import-existing-bom-files) [Revisions Vs BOMs](https://docs.viabom.com/#revisions-vs-boms) [Export](https://docs.viabom.com/#export) [Project Context Changes Search](https://docs.viabom.com/#project-context-changes-search) [Good Working Habits](https://docs.viabom.com/#good-working-habits)