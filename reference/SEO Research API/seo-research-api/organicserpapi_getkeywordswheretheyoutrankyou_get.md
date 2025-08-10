---
title: Get Where They Outrank You Keywords
excerpt: >-
  Returns keywords where the query domain currently outranks the comparison
  domain in organic search results. This endpoint identifies competitive gaps
  where one domain holds a better position than another, providing insights into
  competitor strengths and opportunities for improvement.


  The response includes both domains' ranking data, with the comparison domain's
  metrics appearing in the 'your' fields (yourRank, yourRankChange, yourUrl).
  Use this to analyze competitive positioning, identify content gaps, and
  discover opportunities where competitors are winning.


  **Common Usage Patterns:**

  - Put competitor in `query` and your domain in `compareDomain` to see where
  they outrank you

  - Put your domain in `query` and competitor in `compareDomain` to see where
  you outrank them


  [Visualize this API live on
  SpyFu](https://www.spyfu.com/seo/keywords/domain?query=example.com) _(TODO -
  verify)_
api:
  file: SpyFu.CloudSerp.SerpResearch.Api_seo.json
  operationId: OrganicSerpApi_GetKeywordsWhereTheyOutRankYou_GET
hidden: false
---