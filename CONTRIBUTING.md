# Contributing to The Epstein Files

## Verification Standard

Every entry in this database must be traceable to an official U.S. government document. This is the only rule that matters.

**Accepted source types:**
- `.gov` domain URLs (DOJ, FBI, federal agency sites)
- Federal court records (PACER/courtlistener.com links)
- Congressional records (house.gov, senate.gov)
- Official government PDF/document releases

**Not accepted:**
- News articles (any outlet, any size)
- Books or memoirs
- Social media posts
- Blogs or opinion pieces
- Tabloid reports
- Speculation or inference

If a source is not an official U.S. government document, it will not be accepted. No exceptions.

## Entry Schema

Every entry must conform to this schema:

```json
{
  "id": "string (unique, kebab-case)",
  "name": "string (full name as it appears in source)",
  "role": "string (their role or title relevant to the connection)",
  "connection": "string (factual summary of documented connection, no speculation)",
  "source_name": "string (title of the government document)",
  "source_type": "string (doj | fbi_vault | house_oversight | federal_court | congress)",
  "source_url": "string (direct URL to the official document)",
  "source_date": "string (YYYY-MM-DD of the document's publication/filing date)",
  "added_date": "string (YYYY-MM-DD when added to this database)",
  "verified": true
}
```

**Field requirements:**
- `id`: Unique identifier. Use kebab-case full name + short source descriptor (e.g., `alan-dworkin-doj-filing`)
- `name`: Full name as it appears in the official source document
- `role`: Their role or title as it relates to the documented connection (e.g., "Attorney", "Financier", "Associate")
- `connection`: One to three sentences max. Factual. Based only on what the source says. No inferences.
- `source_name`: Exact title of the document (as shown in the source)
- `source_type`: One of the accepted types listed above
- `source_url`: Must be a direct link to the official document. URL shorteners are not accepted.
- `source_date`: Publication or filing date of the source document
- `added_date`: Date the entry was added to this database
- `verified`: Must be `true` for all entries in the dataset

## PR Requirements

1. **Direct government URL is required.** No exceptions. If the URL does not point to an official government document, the PR will be closed.
2. One entry per PR (or a small batch from the same source document).
3. Follow the schema exactly. Invalid schema = PR closed.
4. The `id` must be unique across the dataset.
5. Entries are added to the `entries` array in `index.html`.

## How Submissions Work

This is a manually curated dataset. There is no automated pipeline. Every PR is reviewed by a human contributor before merging.

To submit a new entry:
1. Add a new object to the `DATA` array in `index.html`
2. Follow the schema exactly (see above)
3. Include a direct link to an official U.S. government document as the source
4. Open a pull request

## Ground Rules

- No speculation. If it isn't in the source document, it isn't in the entry.
- No legal conclusions. This is a reference tool, not a prosecution.
- No tabloid content. News articles are not acceptable sources.
- No inference. "He was mentioned alongside X" is fine. "He must have known" is not.
- Respect the tone. Factual, understated, credible.
