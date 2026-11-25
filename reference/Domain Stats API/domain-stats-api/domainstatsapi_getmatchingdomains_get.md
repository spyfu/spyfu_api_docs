---
title: Find Domains by Pattern and Metrics
excerpt: >-
  Find domains matching wildcard patterns and performance criteria in the current
  month or an inclusive historical month range. Historical metrics use the same
  normalization as Get All Domain Stats.
api:
  file: SpyFu.DomainStats.Research.Api.json
  operationId: DomainStatsApi_GetMatchingDomains_GET
hidden: false
---

Use wildcards such as `*blog*` to find matching domains, then narrow the results
with traffic, budget, ranking, and other metric filters.

## Choose the months to search

**Default:** If both `searchDateId.min` and `searchDateId.max` are omitted, the
endpoint uses `dateId` when supplied, or the current domain stats index otherwise.
It does not default to all historical months.

| Parameters | Months searched |
| --- | --- |
| Neither date bound nor `dateId` supplied | Current month |
| `searchDateId.min` and `searchDateId.max` | Every available month between the bounds, inclusive |
| Only `searchDateId.min` | From that month through the latest available month |
| Only `searchDateId.max` | From the earliest available month through that month |
| `dateId` | One exact historical month |

Use `yyyyMM` values, such as `202609` for September 2026. Set both bounds to the
same value to search one month. The maximum cannot be earlier than the minimum,
and `dateId` cannot be combined with either range bound. Invalid dates or
conflicting parameters return HTTP 400.

For example, search August and September 2026:

```http
GET /apis/domain_stats_api/v2/getMatchingDomains?query=*blog*&searchDateId.min=202608&searchDateId.max=202609
```

With only `searchDateId.max=202609`, the search includes every available month
from the beginning of the available history through September 2026, inclusive.
With only `searchDateId.min=202609`, it includes September 2026 and every
available month after it through the latest available month in the dataset.
The latest available month may lag the calendar month.
Ranges include intermediate years as well as the endpoints. For example,
`searchDateId.min=201601&searchDateId.max=202601` searches all 121 months from
January 2016 through January 2026, where data is available. Missing months in a
range are skipped; a range with no available months returns an empty result.
An unavailable exact month requested with `dateId` returns HTTP 404.

## Historical metrics and pagination

Returned historical metrics use the same normalization as
[Get All Domain Stats](https://developer.spyfu.com/reference/domainstatsapi_getalldomainstats_get), including adjustments
for changes to legacy data, paid-keyword counts, and budget formulas. Metric
filters and sorting use stored monthly values, so normalized response values can
differ from the values used to select and order results.

Each result represents one domain and one month. The same domain can therefore
appear more than once. `totalMatchingResults` counts matching domain/month
records, rather than distinct domains. `pageSize` limits those records per page,
and `startingRow` is 1-based. Use pagination to retrieve additional matching
months; requesting a range does not bypass the page-size limit.
