# Contributing to Health Analysis

Thank you for considering a contribution. This is an analytics project, so contributions look a little different from a typical code repo.

## Ways to contribute

- **Improve the cleaning logic.** If you spot a row in `Raw Data` that should be handled differently in `Clean Data`, open an issue with the Patient ID and the proposed treatment.
- **Add a new view.** New pivot or chart that surfaces something the existing dashboard misses? Fork the workbook, add the sheet, and submit a pull request with a screenshot.
- **Sharpen the documentation.** If a sentence in the README or the PDF deck is unclear, ambiguous, or wrong, open an issue or a pull request with the rewrite.
- **Port to another tool.** Power BI, Tableau, Looker rebuilds are welcome as separate branches with their own README in a `tableau/` or `powerbi-port/` folder.

## How to submit

1. Fork the repository
2. Create a branch named for your change (`fix-age-grouping`, `add-doctor-utilization-view`)
3. Make the change in a copy of the workbook so the original is preserved
4. Update the README if the change affects the structure or the headline findings
5. Open a pull request with a clear description of what changed and why

## What gets accepted

- Changes that improve accuracy, clarity or coverage
- Documentation rewrites that make the work easier to understand
- New analytical views with a stated business question they answer

## What gets declined

- Cosmetic changes to the workbook formatting that do not affect insight
- Changes that strip the data quality flags (the Unknown and Unassigned buckets are intentional)
- Changes that introduce external dependencies without discussion

## Questions

Open an issue with the `question` label or email Bihbrandy15@gmail.com.
