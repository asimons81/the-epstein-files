# The Epstein Files: Exposed

A public investigative reference tool. Each entry links a named individual to Jeffrey Epstein's criminal network, with a direct trace to an official U.S. government document.

## Scope

- **Source-only.** Every entry points to an official U.S. government source: DOJ filings, FBI Vault (FOIA), House Oversight transcripts, or federal court records (PACER).
- **No speculation.** The dataset contains only claims supported by those documents. No rumors, no tabloid material, no legal conclusions.
- **Not a verdict.** This is a reference tool, not a prosecution.

## Data Structure

The entire dataset lives in `index.html` as hardcoded JSON. No backend, no live API, no build step. You can audit the data without running anything.

## Running Locally

```bash
python3 -m http.server 8000
# or
npx serve .
```

Open `http://localhost:8000`.

## Contributing

Submit a pull request. The only hard requirement: a direct link to an official U.S. government document (.gov or federal court record) as the source for each entry.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the entry schema.

## Current Status

This is a static, manually curated reference tool. The dataset is small by design — every entry is reviewed before inclusion. There is no automated pipeline.

## License

MIT — see [LICENSE](LICENSE)