# Source: https://docs.viabom.com/docs/rulesets

# Rulesets

Copy page

Encode cost, lifecycle, qualification, and supply-chain preferences so search ranking reflects how your team actually chooses parts.

Rulesets tell Via what "better" means for your team.

Image placeholder

Add this file to \`apps/docs/public/screenshots/\`

ruleset-view-and-config.png

Capture a ruleset page with multiple rules visible plus version or config controls so the page structure is easy to understand.

The docs will automatically render the real image once this file exists at /screenshots/ruleset-view-and-config.png.

## [What Rulesets Change](https://docs.viabom.com/#what-rulesets-change)

Without a ruleset, search mostly responds to the query itself.

With a ruleset, Via can also account for ongoing preferences like:

- avoid risky lifecycle states
- prefer stocked parts
- require qualification or compliance constraints
- push cost up or down only within acceptable bounds
- keep continuity with already selected manufacturers or families

## [Common Patterns](https://docs.viabom.com/#common-patterns)

Real rulesets often look like combinations of:

- **Require**: `AEC-Q200 certified`, `Temp range >= -40C to +125C`
- **Prefer**: `multi-source parts`, `manufacturer direct stock`
- **Avoid**: `single-source components`, `EOL or NRND`

The exact rule vocabulary can evolve, but the core idea is stable: rulesets let you encode engineering and supply-chain intent once instead of retyping it in every search.

## [Create And Version Rulesets](https://docs.viabom.com/#create-and-version-rulesets)

Rulesets are versioned. That matters because ranking policy changes over time.

Use a new version when:

- procurement priorities changed
- a qualification bar changed
- you want to test a stricter or looser ranking policy

If you need temporary variations on the same base ruleset, keep the underlying ruleset stable and use a separate config/profile where available.

## [Where Rulesets Apply](https://docs.viabom.com/#where-rulesets-apply)

Rulesets are most helpful when they are active inside a project or alongside a library. In those contexts, they can shape ranking automatically instead of acting like a static note someone has to remember.

The ideal flow is automatic: supply-chain or management users define policy, and engineers search in a project or BOM without having to manually select every rule. Via should carry the active project, BOM, library, and default ruleset context into search so engineers can focus on electrical fit while sourcing, lifecycle, and compliance preferences shape the shortlist in the background.

## [Stakeholder Workflows](https://docs.viabom.com/#stakeholder-workflows)

**Supply chain** owns reusable sourcing policy: approved vendors, distributor preferences, stock and lead-time posture, lifecycle risk, MOQ limits, and regional sourcing.

**Management** uses rulesets to standardize decisions across programs, then reviews coverage, exceptions, and policy drift.

**Engineering** benefits most when rulesets are already attached by context. Engineers should see concise explanations like "boosted by approved vendor" or "needs exception: single-source", not be forced to understand every supply-chain rule before searching.

## [How To Use Them Well](https://docs.viabom.com/#how-to-use-them-well)

- keep rules concrete enough to affect decisions
- avoid mixing too many conflicting goals into one ruleset
- create separate versions when policy changed, instead of editing history away
- prefer defaults and project/BOM attachment over manual selection
- compare search behavior before and after major rule changes

## [Current Notes](https://docs.viabom.com/#current-notes)

- ruleset influence is useful, but not perfect yet
- ranking can still need manual judgment, especially for ambiguous queries
- automatic attachment and result-level rule explanations are the key product direction
- if a ruleset obviously overconstrains or misranks the results, report the query and what you expected instead

[Libraries\\ \\ Save preferred parts into reusable libraries so future searches can lean toward parts your team already trusts.](https://docs.viabom.com/docs/libraries) [Workspaces\\ \\ Understand how Via scopes shared projects, libraries, rulesets, and settings to the active organization workspace.](https://docs.viabom.com/docs/workspaces)

### On this page

[What Rulesets Change](https://docs.viabom.com/#what-rulesets-change) [Common Patterns](https://docs.viabom.com/#common-patterns) [Create And Version Rulesets](https://docs.viabom.com/#create-and-version-rulesets) [Where Rulesets Apply](https://docs.viabom.com/#where-rulesets-apply) [Stakeholder Workflows](https://docs.viabom.com/#stakeholder-workflows) [How To Use Them Well](https://docs.viabom.com/#how-to-use-them-well) [Current Notes](https://docs.viabom.com/#current-notes)