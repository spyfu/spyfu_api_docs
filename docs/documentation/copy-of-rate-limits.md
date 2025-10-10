---
title: API Costs
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

| API                                                                                                             | Requests / Sec |
| --------------------------------------------------------------------------------------------------------------- | -------------- |
| [Ad History API](https://developer.spyfu.com/reference/adhistoryapi_getdomainadhistory_get#/)                   | 10             |
| [SEO Research API](https://developer.spyfu.com/reference/organicserpapi_getseokeywords_get#/)*                  | 10             |
| [Competitors API](https://developer.spyfu.com/reference/competitorsapi_gettopppccompetitors_get#/)              | 1000           |
| [Ranking History API](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsfordomain_get#/) | 10             |

*SEO Research API covers both Organic SERP and Top Pages endpoints.

***

## Endpoint-Specific Limits

### [Domain Stats API](https://developer.spyfu.com/reference/domainstatsapi_getalldomainstats_get#/)

| Endpoint                                                                                                                                   | Requests / Sec |
| ------------------------------------------------------------------------------------------------------------------------------------------ | -------------- |
| [/domain\_stats\_api/v2/getAllDomainStats](https://developer.spyfu.com/reference/domainstatsapi_getalldomainstats_get#/)                   | 1000           |
| [/domain\_stats\_api/v2/getLatestDomainStats](https://developer.spyfu.com/reference/domainstatsapi_getlatestdomainstats_get#/)             | 1000           |
| [/domain\_stats\_api/v2/getDomainStatsForExactDate](https://developer.spyfu.com/reference/domainstatsapi_getdomainstatsforexactdate_get#/) | 1000           |
| [/domain\_stats\_api/v2/getActiveDatesForDomain](https://developer.spyfu.com/reference/domainstatsapi_getactivedatesfordomain_get#/)       | 1000           |
| [/domain\_stats\_api/v2/getBulkDomainStats](https://developer.spyfu.com/reference/domainstatsapi_getbulkdomainstats_get#/)                 | 333            |
| [/domain\_stats\_api/v2/getMatchingDomains](https://developer.spyfu.com/reference/domainstatsapi_getmatchingdomains_get#/)                 | 10             |

### [Ad History API](https://developer.spyfu.com/reference/adhistoryapi_getdomainadhistory_get#/) _(uniform: 10 r/s)_

| Endpoint                                                                                                                                         | Requests / Sec |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | -------------- |
| [/cloud\_ad\_history\_api/v2/domain/getDomainAdHistory](https://developer.spyfu.com/reference/adhistoryapi_getdomainadhistory_get#/)             | 10             |
| [/cloud\_ad\_history\_api/v2/term/getTermAdHistory](https://developer.spyfu.com/reference/adhistoryapi_gettermadhistory_get#/)                   | 10             |
| [/cloud\_ad\_history\_api/v2/term/getTermAdHistoryWithStats](https://developer.spyfu.com/reference/adhistoryapi_gettermadhistorywithstats_get#/) | 10             |

### [PPC Research API](https://developer.spyfu.com/reference/paidserpapi_getpaidserps_get#/)

| Endpoint                                                                                                            | Requests / Sec |
| ------------------------------------------------------------------------------------------------------------------- | -------------- |
| [/serp\_api/v2/ppc/getPaidSerps](https://developer.spyfu.com/reference/paidserpapi_getpaidserps_get#/)              | 12             |
| [/keyword\_api/v2/ppc/getMostSuccessful](https://developer.spyfu.com/reference/paidserpapi_getmostsuccessful_get#/) | 10             |
| [/keyword\_api/v2/ppc/getNewKeywords](https://developer.spyfu.com/reference/paidserpapi_getnewkeywords_get#/)       | 10             |

### [SEO Research API](https://developer.spyfu.com/reference/organicserpapi_getseokeywords_get#/) _(uniform: 10 r/s)_

| Endpoint                                                                                                                                          | Requests / Sec |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [/serp\_api/v2/seo/getSeoKeywords](https://developer.spyfu.com/reference/organicserpapi_getseokeywords_get#/)                                     | 10             |
| [/serp\_api/v2/seo/getMostValuableKeywords](https://developer.spyfu.com/reference/organicserpapi_getmostvaluablekeywords_get#/)                   | 10             |
| [/serp\_api/v2/seo/getNewlyRankedKeywords](https://developer.spyfu.com/reference/organicserpapi_getnewlyrankedkeywords_get#/)                     | 10             |
| [/serp\_api/v2/seo/getGainedRanksKeywords](https://developer.spyfu.com/reference/organicserpapi_getgainedrankskeywords_get#/)                     | 10             |
| [/serp\_api/v2/seo/getLostRanksKeywords](https://developer.spyfu.com/reference/organicserpapi_getlostrankskeywords_get#/)                         | 10             |
| [/serp\_api/v2/seo/getGainedClicksKeywords](https://developer.spyfu.com/reference/organicserpapi_getgainedclickskeywords_get#/)                   | 10             |
| [/serp\_api/v2/seo/getLostClicksKeywords](https://developer.spyfu.com/reference/organicserpapi_getlostclickskeywords_get#/)                       | 10             |
| [/serp\_api/v2/seo/getJustMadeItKeywords](https://developer.spyfu.com/reference/organicserpapi_getjustmadeitkeywords_get#/)                       | 10             |
| [/serp\_api/v2/seo/getJustFellOffKeywords](https://developer.spyfu.com/reference/organicserpapi_getjustfelloffkeywords_get#/)                     | 10             |
| [/serp\_api/v2/seo/getSerpAnalysisKeywords](https://developer.spyfu.com/reference/organicserpapi_getserpanalysiskeywords_get#/)                   | 10             |
| [/serp\_api/v2/seo/getWhereTheyOutRankYou](https://developer.spyfu.com/reference/organicserpapi_getkeywordswheretheyoutrankyou_get#/)             | 10             |
| [/serp\_api/v2/seo/getWhereTheyJustSurpassedYou](https://developer.spyfu.com/reference/organicserpapi_getkeywordswheretheyjustsurpassedyou_get#/) | 10             |
| [/serp\_api/v2/seo/getLiveSeoStats](https://developer.spyfu.com/reference/organicserpapi_getliveseostats_get#/)                                   | 10             |
| [/serp\_api/v2/seo/getOrganicOutrankingKeywords](https://developer.spyfu.com/reference/organicserpapi_getorganicoutrankingkeywords_get#/)         | 10             |
| [/serp\_api/v2/seo/getMostTrafficTopPages](https://developer.spyfu.com/reference/toppagesapi_getmosttraffictoppages_get#/)                        | 10             |
| [/serp\_api/v2/seo/getNewTopPages](https://developer.spyfu.com/reference/toppagesapi_getnewtoppages_get#/)                                        | 10             |
| [/serp\_api/v2/seo/getTopPages](https://developer.spyfu.com/reference/toppagesapi_gettoppages_get#/)                                              | 2              |

### [Competitors API](https://developer.spyfu.com/reference/competitorsapi_gettopppccompetitors_get#/) _(uniform: 1000 r/s)_

| Endpoint                                                                                                                                        | Requests / Sec |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [/competitors\_api/v2/ppc/getTopCompetitors](https://developer.spyfu.com/reference/competitorsapi_gettopppccompetitors_get#/)                   | 1000           |
| [/competitors\_api/v2/seo/getTopCompetitors](https://developer.spyfu.com/reference/competitorsapi_gettopseocompetitors_get#/)                   | 1000           |
| [/competitors\_api/v2/combined/getCombinedTopCompetitors](https://developer.spyfu.com/reference/competitorsapi_getcombinedtopcompetitors_get#/) | 1000           |

### [Kombat API](https://developer.spyfu.com/reference/kombatapi_getcompetingppckeywords_get#/)

| Endpoint                                                                                                                         | Requests / Sec |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [/keyword\_api/v2/kombat/getCompetingPpcKeywords](https://developer.spyfu.com/reference/kombatapi_getcompetingppckeywords_get#/) | 10             |
| [/keyword\_api/v2/kombat/getCompetingSeoKeywords](https://developer.spyfu.com/reference/kombatapi_getcompetingseokeywords_get#/) | 8              |

### [Keyword Research API](https://developer.spyfu.com/reference/relatedkeywordsv2api_getrelatedkeywords_get#/)

| Endpoint                                                                                                                                                 | Requests / Sec |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [/keyword\_api/v2/related/getRelatedKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getrelatedkeywords_get#/)                       | 5              |
| [/keyword\_api/v2/related/getQuestionKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getquestionkeywords_get#/)                     | 10             |
| [/keyword\_api/v2/related/getAlsoBuysAdsForKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getalsobuysadsforkeywords_get#/)         | 10             |
| [/keyword\_api/v2/related/getAlsoRanksForKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getalsoranksforkeywords_get#/)             | 10             |
| [/keyword\_api/v2/related/getTransactionKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_gettransactionkeywords_get#/)               | 10             |
| [/keyword\_api/v2/related/getKeywordInformation \[GET\]](https://developer.spyfu.com/reference/relatedkeywordsv2api_getkeywordsbybulksearch_get#/)       | 100            |
| [/keyword\_api/v2/related/getKeywordInformation \[POST\]](https://developer.spyfu.com/reference/relatedkeywordsv2api_getkeywordsbybulksearchpost_post#/) | 10             |
| [/keyword\_api/v2/related/getKeywordExpansions](https://developer.spyfu.com/reference/relatedkeywordsv2api_getkeywordexpansions_get#/)                   | 100            |

### [Ranking History API](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsfordomain_get#/) _(uniform: 10 r/s)_

| Endpoint                                                                                                                                                                        | Requests / Sec |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| [/organic\_history\_api/v2/historic/getHistoricRankingsForDomain](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsfordomain_get#/)                     | 10             |
| [/organic\_history\_api/v2/historic/getHistoricRankingsForKeywordOnDomains](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsforkeywordondomains_get#/) | 10             |
| [/organic\_history\_api/v2/historic/getHistoricRankingsForDomainOnKeywords](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsfordomainonkeywords_get#/) | 10             |

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