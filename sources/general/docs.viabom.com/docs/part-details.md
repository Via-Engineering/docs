# Source: https://docs.viabom.com/docs/part-details

# Part Details

Copy page

Use quick look and part details to verify extracted specs, datasheets, variants, and supply context before committing a part.

Image placeholder

Add this file to \`apps/docs/public/screenshots/\`

part-details-quick-look-modal.png

Capture a real quick look or part-details view with the main specs, actions, and supporting detail clearly visible.

The docs will automatically render the real image once this file exists at /screenshots/part-details-quick-look-modal.png.

Part details are where you confirm that a search result is real, relevant, and safe to use.

## [What To Look For First](https://docs.viabom.com/#what-to-look-for-first)

Start with the basics:

- manufacturer part number
- short summary or UI name
- extracted specifications
- linked datasheet
- package and category context

If those do not line up, stop there and report the issue instead of trusting the result further down the page.

## [Quick Look](https://docs.viabom.com/#quick-look)

Quick look is the fast inspection path when you do not want to fully leave your result list.

Use it to:

- scan the most important specs quickly
- open the datasheet
- jump through adjacent results
- compare a likely candidate before adding it to a project

For keyboard-heavy workflows, the app also exposes quick look shortcuts so you can inspect results without switching back to the mouse constantly.

## [Extracted Specs](https://docs.viabom.com/#extracted-specs)

Via pulls structured values out of datasheets so you can compare parts without reading every PDF from scratch.

Treat extracted values as useful decision support:

- some specs will still be missing
- units may occasionally need correction
- condition-specific values can be flattened too aggressively

When a value matters to a design decision, cross-check it against the linked datasheet.

## [Datasheets](https://docs.viabom.com/#datasheets)

The part view links back to the source datasheet when one is available. Use the datasheet to verify:

- absolute maximum ratings
- recommended operating conditions
- package and footprint specifics
- lifecycle or qualification claims
- tables and curves that are too detailed to summarize well

If the link is wrong or the PDF is clearly unrelated, file a report.

## [Series Navigation And Equivalents](https://docs.viabom.com/#series-navigation-and-equivalents)

Some parts include series-aware navigation. This is useful when the part is close but not quite right and you want to stay within the same family instead of starting over.

Look for series tools when you want to:

- move to a nearby value or rating
- compare same-family package options
- check known equivalent or neighboring variants

This is especially helpful for passives and families with predictable variant steps.

## [Distributor Snapshot](https://docs.viabom.com/#distributor-snapshot)

When Via has distributor context available, you can use it to sanity-check:

- stock state
- minimum order quantity
- order multiple
- pricing tiers
- freshness of the listing snapshot

Do not treat the snapshot as a purchasing system of record. It is a decision aid inside the part workflow.

## [Design Calculators](https://docs.viabom.com/#design-calculators)

Some parts include datasheet-driven design calculators. When present, use them to validate or estimate values that would otherwise require manual datasheet math.

These calculators are especially useful as a first-pass check before deeper design review.

## [When To Report A Problem](https://docs.viabom.com/#when-to-report-a-problem)

Report the part when:

- the part identity is wrong
- key extracted values are obviously incorrect
- the linked datasheet is wrong or missing
- series navigation points to nonsense neighbors
- distributor details are misleading enough to change a decision

The feedback flow can attach the current part and search context, so include the specific field that looks wrong and what you expected to see instead.

[Search\\ \\ Search with part numbers, specs, and natural language, then refine the results with filters, context, and ranking cues.](https://docs.viabom.com/docs/search) [Projects & BOMs\\ \\ Organize selected parts into projects, revisions, and BOMs, then import, refine, and export your working bill of materials.](https://docs.viabom.com/docs/projects-and-boms)

### On this page

[What To Look For First](https://docs.viabom.com/#what-to-look-for-first) [Quick Look](https://docs.viabom.com/#quick-look) [Extracted Specs](https://docs.viabom.com/#extracted-specs) [Datasheets](https://docs.viabom.com/#datasheets) [Series Navigation And Equivalents](https://docs.viabom.com/#series-navigation-and-equivalents) [Distributor Snapshot](https://docs.viabom.com/#distributor-snapshot) [Design Calculators](https://docs.viabom.com/#design-calculators) [When To Report A Problem](https://docs.viabom.com/#when-to-report-a-problem)