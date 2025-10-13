---
title: SpyFu API Pricing
deprecated: false
hidden: true
metadata:
  robots: index
---
# API Endpoint Pricing

Access to the API is included with the **SpyFu Pro + AI** and **Team/Agency** subscription plan. The **Pro + AI** subscription includes a **$40 monthly API credit** and the **Team/Agency** subscription includes a **$100 monthly API credit**. The SpyFu API operates on a Pay-as-you-Go pricing model.

<b><u><i>IMPORTANT:</i></u></b> API charges are based on the number of rows returned per request submitted to an API endpoint. Each API endpoint is priced individually based on the computational cost to return a row of data. Many of the endpoints return more than 1 result row per request. Please see the **API Endpoints Pricing Guide** below for the specific **CPM** (cost per thousand) of each returned row.

***

## API Billing

API billing is calculated on a monthly basis, starting the first day of each month at 00:00 AM UTC and ending on the last day of each month at 11:59 PM UTC.

The bill amount is calculated from the number of successful rows returned from each API endpoint, divided by 1000, multiplied by the CPM for that endpoint. Those individual endpoint totals are added together, any applicable API credit is then subtracted from the total, and the remaining balance is charged to the payment method on file with SpyFu.

THIS SECTION IS FOR EXPLANATION OF INCREMENTAL BILLING\< IF USED

API usage and billing can be monitored via the API Usage tab in the My Account section of the website: [https://www.spyfu.com/account/api](https://www.spyfu.com/account/api)

Live API usage can also be monitored via the Account API which is documented here: [Account API](ref:account-api)

***

## SpyFu API Endpoints Pricing Guide

Single/Multiple* - Denotes the endpoint can return single or multiple rows, and by default will return multiple rows.

### [Domain Stats API](https://developer.spyfu.com/reference/domainstatsapi_getalldomainstats_get#/)

| Endpoint                                                                                                                                 | Rows Returned    | CPM   |
| ---------------------------------------------------------------------------------------------------------------------------------------- | :--------------- | ----- |
| [/domain_stats_api/v2/getAllDomainStats](https://developer.spyfu.com/reference/domainstatsapi_getalldomainstats_get#/)                   | Multiple         | $0.50 |
| [/domain_stats_api/v2/getLatestDomainStats](https://developer.spyfu.com/reference/domainstatsapi_getlatestdomainstats_get#/)             | Single/Multiple* | $0.50 |
| [/domain_stats_api/v2/getDomainStatsForExactDate](https://developer.spyfu.com/reference/domainstatsapi_getdomainstatsforexactdate_get#/) | Single           | $0.50 |
| [/domain_stats_api/v2/getActiveDatesForDomain](https://developer.spyfu.com/reference/domainstatsapi_getactivedatesfordomain_get#/)       | Multiple         | $0.50 |
| [/domain_stats_api/v2/getBulkDomainStats](https://developer.spyfu.com/reference/domainstatsapi_getbulkdomainstats_get#/)                 | Single/Multiple  | $0.40 |
| [/domain_stats_api/v2/getMatchingDomains](https://developer.spyfu.com/reference/domainstatsapi_getmatchingdomains_get#/)                 | Multiple         | $1.00 |

### [Ad History API](https://developer.spyfu.com/reference/adhistoryapi_getdomainadhistory_get#/)

| Endpoint                                                                                                                                      | Rows Returned | CPM   |
| --------------------------------------------------------------------------------------------------------------------------------------------- | :------------ | ----- |
| [/cloud_ad_history_api/v2/domain/getDomainAdHistory](https://developer.spyfu.com/reference/adhistoryapi_getdomainadhistory_get#/)             | Multiple      | $3.00 |
| [/cloud_ad_history_api/v2/term/getTermAdHistory](https://developer.spyfu.com/reference/adhistoryapi_gettermadhistory_get#/)                   | Multiple      | $3.00 |
| [/cloud_ad_history_api/v2/term/getTermAdHistoryWithStats](https://developer.spyfu.com/reference/adhistoryapi_gettermadhistorywithstats_get#/) | Multiple      | $3.00 |

### [PPC Research API](https://developer.spyfu.com/reference/paidserpapi_getpaidserps_get#/)

| Endpoint                                                                                                           | Rows Returned    | CPM   |
| ------------------------------------------------------------------------------------------------------------------ | :--------------- | ----- |
| [/serp_api/v2/ppc/getPaidSerps](https://developer.spyfu.com/reference/paidserpapi_getpaidserps_get)                | Single/Multiple* | $2.00 |
| [/keyword_api/v2/ppc/getMostSuccessful](https://developer.spyfu.com/reference/paidserpapi_getmostsuccessful_get#/) | Single/Multiple* | $2.00 |
| [/keyword_api/v2/ppc/getNewKeywords](https://developer.spyfu.com/reference/paidserpapi_getnewkeywords_get#/)       | Single/Multiple* | $2.00 |

### [SEO Research API](https://developer.spyfu.com/reference/organicserpapi_getseokeywords_get#/)

| Endpoint                                                                                                                                         | Rows Returned    | CPM   |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------- | ----- |
| [/serp_api/v2/seo/getSeoKeywords](https://developer.spyfu.com/reference/organicserpapi_getseokeywords_get#/)                                     | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getMostValuableKeywords](https://developer.spyfu.com/reference/organicserpapi_getmostvaluablekeywords_get#/)                   | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getNewlyRankedKeywords](https://developer.spyfu.com/reference/organicserpapi_getnewlyrankedkeywords_get#/)                     | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getGainedRanksKeywords](https://developer.spyfu.com/reference/organicserpapi_getgainedrankskeywords_get#/)                     | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getLostRanksKeywords](https://developer.spyfu.com/reference/organicserpapi_getlostrankskeywords_get#/)                         | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getGainedClicksKeywords](https://developer.spyfu.com/reference/organicserpapi_getgainedclickskeywords_get#/)                   | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getLostClicksKeywords](https://developer.spyfu.com/reference/organicserpapi_getlostclickskeywords_get#/)                       | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getJustMadeItKeywords](https://developer.spyfu.com/reference/organicserpapi_getjustmadeitkeywords_get#/)                       | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getJustFellOffKeywords](https://developer.spyfu.com/reference/organicserpapi_getjustfelloffkeywords_get#/)                     | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getSerpAnalysisKeywords](https://developer.spyfu.com/reference/organicserpapi_getserpanalysiskeywords_get#/)                   | Single/Multiple* | $0.50 |
| [/serp_api/v2/seo/getWhereTheyOutRankYou](https://developer.spyfu.com/reference/organicserpapi_getkeywordswheretheyoutrankyou_get#/)             | Single/Multiple* | $2.00 |
| [/serp_api/v2/seo/getWhereTheyJustSurpassedYou](https://developer.spyfu.com/reference/organicserpapi_getkeywordswheretheyjustsurpassedyou_get#/) | Single/Multiple* | $2.00 |
| [/serp_api/v2/seo/getLiveSeoStats](https://developer.spyfu.com/reference/organicserpapi_getliveseostats_get#/)                                   | Single           | $1.00 |
| [/serp_api/v2/seo/getMostTrafficTopPages](https://developer.spyfu.com/reference/toppagesapi_getmosttraffictoppages_get#/)                        | Single/Multiple* | $5.00 |
| [/serp_api/v2/seo/getNewTopPages](https://developer.spyfu.com/reference/toppagesapi_getnewtoppages_get#/)                                        | Single/Multiple* | $5.00 |
| [/serp_api/v2/seo/getOrganicOutrankingKeywords](https://developer.spyfu.com/reference/organicserpapi_getorganicoutrankingkeywords_get#/)         | Single/Multiple* | $2.00 |
| [/serp_api/v2/seo/getTopPages](https://developer.spyfu.com/reference/toppagesapi_gettoppages_get#/)                                              | Single/Multiple* | $5.00 |

### [Competitors API](https://developer.spyfu.com/reference/competitorsapi_gettopppccompetitors_get#/)

| Endpoint                                                                                                                                       | Rows Returned    | CPM   |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | :--------------- | ----- |
| [/competitors_api/v2/ppc/getTopCompetitors](https://developer.spyfu.com/reference/competitorsapi_gettopppccompetitors_get#/)                   | Single/Multiple* | $0.20 |
| [/competitors_api/v2/seo/getTopCompetitors](https://developer.spyfu.com/reference/competitorsapi_gettopseocompetitors_get#/)                   | Single/Multiple* | $0.20 |
| [/competitors_api/v2/combined/getCombinedTopCompetitors](https://developer.spyfu.com/reference/competitorsapi_getcombinedtopcompetitors_get#/) | Single/Multiple* | $0.20 |

### [Kombat API](https://developer.spyfu.com/reference/kombatapi_getcompetingppckeywords_get#/)

| Endpoint                                                                                                                        | Rows Returned    | CPM   |
| ------------------------------------------------------------------------------------------------------------------------------- | :--------------- | ----- |
| [/keyword_api/v2/kombat/getCompetingPpcKeywords](https://developer.spyfu.com/reference/kombatapi_getcompetingppckeywords_get#/) | Single/Multiple* | $1.00 |
| [/keyword_api/v2/kombat/getCompetingSeoKeywords](https://developer.spyfu.com/reference/kombatapi_getcompetingseokeywords_get#/) | Single/Multiple* | $1.00 |

### [Keyword Research API](https://developer.spyfu.com/reference/relatedkeywordsv2api_getrelatedkeywords_get#/)

| Endpoint                                                                                                                                              | Rows Returned    | CPM   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------- | ----- |
| [/keyword_api/v2/related/getRelatedKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getrelatedkeywords_get#/)                     | Single/Multiple* | $2.50 |
| [/keyword_api/v2/related/getQuestionKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getquestionkeywords_get#/)                   | Single/Multiple* | $1.00 |
| [/keyword_api/v2/related/getAlsoBuysAdsForKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getalsobuysadsforkeywords_get#/)       | Single/Multiple* | $1.00 |
| [/keyword_api/v2/related/getAlsoRanksForKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_getalsoranksforkeywords_get#/)           | Single/Multiple* | $1.00 |
| [/keyword_api/v2/related/getTransactionKeywords](https://developer.spyfu.com/reference/relatedkeywordsv2api_gettransactionkeywords_get#/)             | Single/Multiple* | $1.00 |
| [/keyword_api/v2/related/getKeywordInformation [GET]](https://developer.spyfu.com/reference/relatedkeywordsv2api_getkeywordsbybulksearch_get#/)       | Single/Multiple  | $0.20 |
| [/keyword_api/v2/related/getKeywordInformation [POST]](https://developer.spyfu.com/reference/relatedkeywordsv2api_getkeywordsbybulksearchpost_post#/) | Single/Multiple  | $0.20 |
| [/keyword_api/v2/related/getKeywordExpansions](https://developer.spyfu.com/reference/relatedkeywordsv2api_getkeywordexpansions_get#/)                 | Single/Multiple* | $1.00 |

### [Ranking History API](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsfordomain_get#/)

| Endpoint                                                                                                                                                                      | Rows Returned    | CPM   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------- | ----- |
| [/organic_history_api/v2/historic/getHistoricRankingsForDomain](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsfordomain_get#/)                     | Single/Multiple* | $3.00 |
| [/organic_history_api/v2/historic/getHistoricRankingsForKeywordOnDomains](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsforkeywordondomains_get#/) | Single/Multiple  | $3.00 |
| [/organic_history_api/v2/historic/getHistoricRankingsForDomainOnKeywords](https://developer.spyfu.com/reference/historicranking_gethistoricrankingsfordomainonkeywords_get#/) | Single/Multiple  | $3.00 |

***

## Questions?

If you need help understanding our API pricing or your API charges, please contact SpyFu support via Live Chat or [support@spyfu.com](mailto:support@spyfu.com).

Need a custom data solution, or help setting up your account? [Pick a Time](https://go.oncehub.com/spyfu)
