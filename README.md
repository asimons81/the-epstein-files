# The Epstein Files: Exposed

A public investigative reference tool documenting connections between named individuals and Jeffrey Epstein's criminal network, sourced exclusively from official U.S. government documents.

## What This Is

- **A reference tool.** Each entry documents a named individual's connection to Epstein's network, traceable to a specific official government source.
- **Source-only sourcing.** Every entry links directly to an official U.S. government document — DOJ filings, FBI Vault releases, House Oversight transcripts, or federal court records.
- **Open and auditable.** The entire dataset is in `index.html` as hardcoded JSON. No backend, no live API, no black box.

## What This Is NOT

- This tool does **not** contain speculation, rumor, or tabloid content.
- It does **not** make legal conclusions about any individual.
- It does **not** include claims that cannot be traced to an official U.S. government source.
- It is **not** a prosecution or a verdict.

## Data Sources

All entries trace to official U.S. government documents, including:

- U.S. Department of Justice (DOJ) court filings and press releases
- FBI Freedom of Information Act (FOIA) releases via FBI Vault
- U.S. House Committee on Oversight and Reform documents
- U.S. federal court records (PACER)

## The Automated Pipeline

`epstein-monitor` is an automated pipeline that runs weekly to detect new government document releases related to Epstein's network.

**How it works:**

1. **Redwood** monitors designated government source feeds (DOJ, FBI Vault, House Oversight, USCourts) on a weekly schedule.
2. **Briar** evaluates new documents for relevance and extracts structured data.
3. **Flint** verifies citations, checks for duplicates, and validates source URLs.
4. **Spark** opens a verified pull request with the new entry against this repository.

PRs opened by the pipeline include the full government source URL and are ready for community review.

## How to Contribute

New entries are welcome. The only requirement: **a direct link to an official U.S. government document (.gov or official court record) as the source.**

See [CONTRIBUTING.md](CONTRIBUTING.md) for the entry schema and submission process.

## For Developers

This is a single HTML file with no build step.

```bash
# Run locally — any static server works
python3 -m http.server 8000
# or
npx serve .
```

Open `http://localhost:8000` in your browser.

## License

MIT — see [LICENSE](LICENSE)
