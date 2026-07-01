# Source: https://docs.viabom.com/docs/search

# Search

Copy page

Search with part numbers, specs, and natural language, then refine the results with filters, context, and ranking cues.

Image placeholder

Add this file to \`apps/docs/public/screenshots/\`

search-results-natural-language-query.png

Capture a representative natural-language search with visible query tags, result columns, and enough rows to show how the ranking behaves.

The docs will automatically render the real image once this file exists at /screenshots/search-results-natural-language-query.png.

Via search is designed to handle the way engineers actually search: partial part numbers, package sizes, spec fragments, and plain-language intent in one query.

## [Start With Real Queries](https://docs.viabom.com/#start-with-real-queries)

- `100nF 0402 capacitor`
- `INA228 current sensor`
- `low-noise LDO 3.3V`
- `rs485 transceiver 3.3v`
- `1% 10k 0402 resistor`

These work because Via tries to interpret both structured clues and free text at the same time.

## [What Search Understands Well](https://docs.viabom.com/#what-search-understands-well)

- part numbers and family names
- common package sizes
- typical spec/value patterns
- natural-language component descriptions
- manufacturer names when they are part of the query

## [Filters And Ranking](https://docs.viabom.com/#filters-and-ranking)

Search results can combine:

- **category cues**
- **manufacturer filters**
- **parameter filters**
- **package cues**
- **ranking preferences**

In practice, that means you can search broadly first and then narrow the results, or start with a more constrained query immediately.

## [Read The Results, Not Just The Top Row](https://docs.viabom.com/#read-the-results-not-just-the-top-row)

When you scan a result list, check:

- part number and manufacturer
- summary or UI name
- which columns look strongest for your current decision
- whether the result actually satisfies the filters you care about

Top-ranked does not always mean "correct enough to ship." Treat the list as a shortlist generator, then confirm on the part details view.

## [Search Context Matters](https://docs.viabom.com/#search-context-matters)

Search behaves differently depending on where you launch it from.

### [Inside a project](https://docs.viabom.com/#inside-a-project)

Via can use your active BOM and ruleset as context, which helps it preserve continuity with the rest of the design.

### [Inside a library](https://docs.viabom.com/#inside-a-library)

Via can bias toward parts already saved in the library or toward nearby trusted families and manufacturers.

### [With an active ruleset](https://docs.viabom.com/#with-an-active-ruleset)

Ranking can be pushed toward cost, stock, lifecycle, qualification, or other preferences your team already encoded.

## [When Results Look Wrong](https://docs.viabom.com/#when-results-look-wrong)

Try these in order:

1. simplify the query to the part family or most important requirement
2. remove extra adjectives and restate the core value/package
3. search from outside the current project or library if the context feels too restrictive
4. open quick look on a near miss and use series navigation before starting over

If the result set is obviously wrong, report the query and what you expected.

## [Current Notes](https://docs.viabom.com/#current-notes)

Search is already useful across a wide range of categories, but the quality bar is still moving in some areas:

- some categories are much better than others
- missing source data can hurt ranking
- the right answer may appear lower than it should
- no-result recovery is improving, but not finished

When accuracy matters, confirm the final candidate on the part details view and datasheet.

[Getting Started\\ \\ Get into Via quickly: sign in, choose a workspace, run a search, and create your first project.](https://docs.viabom.com/docs/getting-started) [Part Details\\ \\ Use quick look and part details to verify extracted specs, datasheets, variants, and supply context before committing a part.](https://docs.viabom.com/docs/part-details)

### On this page

[Start With Real Queries](https://docs.viabom.com/#start-with-real-queries) [What Search Understands Well](https://docs.viabom.com/#what-search-understands-well) [Filters And Ranking](https://docs.viabom.com/#filters-and-ranking) [Read The Results, Not Just The Top Row](https://docs.viabom.com/#read-the-results-not-just-the-top-row) [Search Context Matters](https://docs.viabom.com/#search-context-matters) [Inside a project](https://docs.viabom.com/#inside-a-project) [Inside a library](https://docs.viabom.com/#inside-a-library) [With an active ruleset](https://docs.viabom.com/#with-an-active-ruleset) [When Results Look Wrong](https://docs.viabom.com/#when-results-look-wrong) [Current Notes](https://docs.viabom.com/#current-notes)