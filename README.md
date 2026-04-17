# Duunitori Scraper

Extract structured data from [Duunitori.fi](https://Duunitori.fi) — structured job listings from Duunitori.fi — Finland's largest job board. Salary ranges, employment types, employer details, and 22,000+ active listings.

**[Duunitori Scraper - Finland Job Listings on Apify →](https://apify.com/blackfalcondata/duunitori-scraper)**

---

## Key features




**Search with filters** — Search by keyword and location.

**Detail enrichment** — Fetch full job descriptions, salary data, direct apply URLs for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

---

## Use cases




**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from duunitori.fi on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from duunitori.fi.

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

---

## Related products by Black Falcon Data




- [StepStone Scraper](https://github.com/BlackFalconData-org/stepstone-scraper) — Job listings from 18 European portals
- [Indeed Job Scraper](https://github.com/BlackFalconData-org/indeed-job-scraper) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://github.com/BlackFalconData-org/glassdoor-job-scraper) — Glassdoor listings with company ratings

---

*Last updated: 2026 03*
