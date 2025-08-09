---
title: Get Keywords Where They Just Surpassed You
excerpt: >-
  Returns keywords where the query domain recently surpassed the comparison
  domain in organic search rankings. This endpoint identifies competitive shifts
  where one domain has overtaken another, either through ranking improvements,
  competitor declines, or both.


  The response includes both domains' ranking data, with the comparison domain's
  metrics appearing in the 'your' fields (yourRank, yourRankChange, yourUrl).
  Use this to monitor competitive threats or analyze successful competitor
  strategies.


  **Common Usage Patterns:**

  - Put competitor in `query` and your domain in `compareDomain` to see where
  they're overtaking you

  - Put your domain in `query` and competitor in `compareDomain` to see where
  you're gaining ground


  [Visualize this API live on
  SpyFu](https://www.spyfu.com/seo/keywords/domain?query=example.com)
api:
  file: SpyFu.CloudSerp.SerpResearch.Api_seo.json
  operationId: OrganicSerpApi_GetKeywordsWhereTheyJustSurpassedYou_GET
hidden: false
---