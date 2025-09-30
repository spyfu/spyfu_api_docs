---
title: Rate Limits
deprecated: false
hidden: true
metadata:
  robots: index
---
# API Rate Limits

To ensure fair usage and system stability, our API enforces **rate limits**. Each endpoint has a maximum number of requests allowed per second. When the limit is exceeded, requests are throttled and the API returns `429 Too Many Requests`.

***

## How Rate Limits Work

* **Per‑endpoint limits**: Each API method has its own requests‑per‑second (RPS) allowance.
* **Window**: Limits apply over a rolling **1‑second** window.
* **Retry**: If you exceed the limit, wait **1 second** before retrying (see `Retry‑After` header).
* **Why different limits?** Heavier endpoints allow fewer requests per second based on relative compute cost.

**Example 429 response**

```http
HTTP/1.1 429 Too Many Requests
Retry-After: 1
Content-Type: application/json
```

```json
{
  "error": "rate_limited",
  "message": "Too many requests. Please retry after 1 second."
}
```

***

## API-Level Overview (Uniform Limits)

Some APIs have the same limit across all listed endpoints.

| API                 | Requests / Sec |
| ------------------- | -------------- |
| Ad History API      | 10             |
| SEO Research API*   | 10             |
| Competitors API     | 1000           |
| Ranking History API | 10             |

*SEO Research API covers both Organic SERP and Top Pages endpoints.

***

## Endpoint-Specific Limits

### Domain Stats API

| Endpoint                   | Requests / Sec |
| -------------------------- | -------------- |
| getAllDomainStats          | 1000           |
| getLatestDomainStats       | 1000           |
| getDomainStatsForExactDate | 1000           |
| getActiveDatesForDomain    | 1000           |
| getBulkDomainStats         | 333            |
| getMatchingDomains         | 10             |

### Ad History API _(uniform: 10 r/s)_

| Endpoint                  | Requests / Sec |
| ------------------------- | -------------- |
| getDomainAdHistory        | 10             |
| getTermAdHistory          | 10             |
| getTermAdHistoryWithStats | 10             |

### PPC Research API

| Endpoint          | Requests / Sec |
| ----------------- | -------------- |
| getPaidSerps      | 12             |
| getMostSuccessful | 10             |
| getNewKeywords    | 10             |

### SEO Research API _(uniform: 10 r/s)_

| Endpoint                     | Requests / Sec |
| ---------------------------- | -------------- |
| getSeoKeywords               | 10             |
| getMostValuableKeywords      | 10             |
| getNewlyRankedKeywords       | 10             |
| getGainedRanksKeywords       | 10             |
| getLostRanksKeywords         | 10             |
| getGainedClicksKeywords      | 10             |
| getLostClicksKeywords        | 10             |
| getJustMadeItKeywords        | 10             |
| getJustFellOffKeywords       | 10             |
| getSerpAnalysisKeywords      | 10             |
| getWhereTheyOutRankYou       | 10             |
| getWhereTheyJustSurpassedYou | 10             |
| getLiveSeoStats              | 10             |
| getOrganicOutrankingKeywords | 10             |
| getMostTrafficTopPages       | 10             |
| getNewTopPages               | 10             |
| getTopPages                  | 2              |

### Competitors API _(uniform: 1000 r/s)_

| Endpoint                  | Requests / Sec |
| ------------------------- | -------------- |
| getTopCompetitors         | 1000           |
| getCombinedTopCompetitors | 1000           |

### Kombat API

| Endpoint                | Requests / Sec |
| ----------------------- | -------------- |
| getCompetingPpcKeywords | 10             |
| getCompetingSeoKeywords | 8              |

### Keyword API

| Endpoint                    | Requests / Sec |
| --------------------------- | -------------- |
| getRelatedKeywords          | 5              |
| getQuestionKeywords         | 10             |
| getAlsoBuysAdsForKeywords   | 10             |
| getAlsoRanksForKeywords     | 10             |
| getTransactionKeywords      | 10             |
| getKeywordInformation       | 100            |
| getKeywordsByBulkSearchPost | 10             |
| getKeywordExpansions        | 100            |

### Ranking History API _(uniform: 10 r/s)_

| Endpoint                               | Requests / Sec |
| -------------------------------------- | -------------- |
| getHistoricRankingsForDomain           | 10             |
| getHistoricRankingsForKeywordOnDomains | 10             |
| getHistoricRankingsForDomainOnKeywords | 10             |

***

## Client Recommendations

* **Backoff on 429**: Retry after the number of seconds indicated by `Retry‑After` (typically `1`).
* **Batch or paginate** where supported to reduce call volume.
* **Cache** results to avoid redundant calls.
* **Parallelism**: Cap concurrency so per‑endpoint RPS stays within limit.

***

## Questions?

If you need a higher limit for specific workloads, contact support with:

* The API and endpoint,
* Expected sustained RPS and burst behavior,
* Use case and time window.
