# Duunitori Scraper

Extract structured data from [Duunitori.fi](https://Duunitori.fi) — structured job listings from Duunitori.fi — Finland's largest job board. Salary ranges, employment types, employer details, and 22,000+ active listings.

**[Duunitori Scraper - Finland Job Listings on Apify →](https://apify.com/blackfalcondata/duunitori-scraper?fpr=1h3gvi)**

---

## Key features





**Search with filters** — Search by keyword and location.

**Detail enrichment** — Fetch full job descriptions, salary data, direct apply URLs for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

**Change classification** — Track cross-run repost detection across runs. Build audit trails of how listings evolve over time.

**Compact output** — Emit core fields only (AI-agent / MCP-friendly). Keeps response size small for LLM workflows.

**Description truncation** — Cap description length per listing to control output size and cost.

**Result cap** — Stop after N listings (up to 1.000). Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases





**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from duunitori.fi on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from duunitori.fi.

**Change monitoring**
Run daily or hourly in incremental mode to capture only new, updated, or expired listings. Perfect for price-tracking, churn analysis, and alerting pipelines.

**Compensation benchmarking**
Aggregate salary ranges across roles, industries, and locations on duunitori.fi to inform pricing decisions, hiring plans, or candidate negotiations.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
{
  "query": "ohjelmistokehittäjä",
  "location": "Helsinki",
  "maxResults": 10,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `query` | string | — | Job search keywords. Leave empty to fetch all jobs. |
| `location` | string | — | City or region in Finland (e.g. Helsinki, Tampere, Turku, Oulu). |
| `maxResults` | integer | `50` | Maximum total results (0 = unlimited). |
| `includeDetails` | boolean | `true` | Fetch full job details from each listing page (salary, employment type, expiry date). |
| `descriptionMaxLength` | integer | `0` | Truncate description to N chars. 0 = no truncation. |
| `compact` | boolean | `false` | Core fields only (for AI-agent/MCP workflows). |
| `incrementalMode` | boolean | `false` | Compare against previous run state — output only new/changed listings. |
| `stateKey` | string | — | Stable identifier for tracked universe. |

---

## FAQ

**How to scrape duunitori?**
Use this actor on Apify to extract structured data from Duunitori.fi. Set your search query and filters in the input, then run — no coding needed.

**Is there a duunitori API?**
Duunitori.fi does not offer a structured data export. This actor works as an unofficial API, returning structured JSON data from duunitori.

**Is it legal to scrape Duunitori.fi?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check the target site's terms of service for your specific use case.

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->


## Output fields

Every listing returns the same 24-field schema. Missing values are `null` — never omitted.

- `jobId`
- `title`
- `company`
- `companyLogoUrl`
- `location`
- `latitude`
- `longitude`
- `salaryText`
- `salaryMin`
- `salaryMax`
- `salaryCurrency`
- `salaryPeriod`
- `employmentType`
- `description`
- `category`
- `occupation`
- `url`
- `portalUrl`
- `applyUrl`
- `directApply`
- `postedDate`
- `validThrough`
- `scrapedAt`
- `source`


## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "jobId": "20116266",
  "title": "Myyjä - Kylpyhuoneremontit",
  "company": "TNT Rekrytointi Oy",
  "companyLogoUrl": "https://duunitori.imgix.net/media/images/logos/TNT_Rekrytointi.png?auto=format&w=300",
  "location": "Tampere",
  "latitude": null,
  "longitude": null,
  "salaryText": "1000–8000 EUR/MONTH",
  "salaryMin": 1000,
  "salaryMax": 8000,
  "salaryCurrency": "EUR",
  "salaryPeriod": "MONTH"
}
```

*Truncated — full records contain 24 fields. See Output fields for the complete schema.*


**[Try Duunitori Scraper - Finland Job Listings now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/duunitori-scraper?fpr=1h3gvi)**


## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.01 |
| Result | $0.002 |

See the [actor on Apify](https://apify.com/blackfalcondata/duunitori-scraper?fpr=1h3gvi) for current pricing.

---

## Related products by Black Falcon Data





- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board
- [Naukri Scraper](https://apify.com/blackfalcondata/naukri-scraper?fpr=1h3gvi) — India's largest job portal


## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) — $5 credit included
2. Open the actor and paste your input
3. Click Start — results download as JSON, CSV, or Excel

Need more volume? [See pricing](https://apify.com/pricing?fpr=1h3gvi).

---


## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---
---

*Last updated: 2026 03*
