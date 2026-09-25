# @llmpulse/sdk@1.48.0

A TypeScript SDK client for the api.llmpulse.ai API.

## Usage

First, install the SDK from npm.

```bash
npm install @llmpulse/sdk --save
```

Next, try it out.


```ts
import {
  Configuration,
  AIAgentTrafficApi,
} from '@llmpulse/sdk';
import type { GetAgentTrafficRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIAgentTrafficApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // string | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) (optional)
    bot: bot_example,
    // string | Filter by company (e.g. openai, anthropic, google) (optional)
    company: company_example,
    // 'bot' | 'company' (optional)
    groupBy: groupBy_example,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
  } satisfies GetAgentTrafficRequest;

  try {
    const data = await api.getAgentTraffic(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```


## Documentation

### API Endpoints

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Class | Method | HTTP request | Description
| ----- | ------ | ------------ | -------------
*AIAgentTrafficApi* | [**getAgentTraffic**](docs/AIAgentTrafficApi.md#getagenttraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta)
*AIAgentTrafficApi* | [**getAiTraffic**](docs/AIAgentTrafficApi.md#getaitraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above)
*AIAgentTrafficApi* | [**listAgentBots**](docs/AIAgentTrafficApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above)
*AIModelInsightsApi* | [**getAiModelInsightsSummary**](docs/AIModelInsightsApi.md#getaimodelinsightssummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary
*AIModelInsightsApi* | [**getAiModelPositionDistribution**](docs/AIModelInsightsApi.md#getaimodelpositiondistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison
*AIModelInsightsApi* | [**getAiOverviewResults**](docs/AIModelInsightsApi.md#getaioverviewresults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability
*AccountApi* | [**getAccount**](docs/AccountApi.md#getaccount) | **GET** /account | Account plan, quota usage and rate limits
*AnnotationsApi* | [**createAnnotation**](docs/AnnotationsApi.md#createannotationoperation) | **POST** /annotations | Create a timeline annotation
*AnnotationsApi* | [**deleteAnnotation**](docs/AnnotationsApi.md#deleteannotation) | **DELETE** /annotations/{id} | Delete a timeline annotation
*AnnotationsApi* | [**listAnnotations**](docs/AnnotationsApi.md#listannotations) | **GET** /annotations | List timeline annotations
*AnnotationsApi* | [**updateAnnotation**](docs/AnnotationsApi.md#updateannotationoperation) | **PATCH** /annotations/{id} | Update a timeline annotation
*AnswersApi* | [**getAnswer**](docs/AnswersApi.md#getanswer) | **GET** /answers/{id} | Get one AI response
*AnswersApi* | [**listAnswers**](docs/AnswersApi.md#listanswers) | **GET** /answers | List AI responses
*CollectionsTagsApi* | [**assignPromptTags**](docs/CollectionsTagsApi.md#assignprompttagsoperation) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts
*CollectionsTagsApi* | [**createCollection**](docs/CollectionsTagsApi.md#createcollectionoperation) | **POST** /collections | Create a tag
*CollectionsTagsApi* | [**deleteCollection**](docs/CollectionsTagsApi.md#deletecollection) | **DELETE** /collections/{id} | Delete a tag
*CollectionsTagsApi* | [**listCollections**](docs/CollectionsTagsApi.md#listcollections) | **GET** /dimensions/collections | List tags/collections
*CollectionsTagsApi* | [**listTags**](docs/CollectionsTagsApi.md#listtags) | **GET** /dimensions/tags | List tags (alias for /collections)
*CollectionsTagsApi* | [**updateCollection**](docs/CollectionsTagsApi.md#updatecollectionoperation) | **PATCH** /collections/{id} | Update a tag
*CompetitorsApi* | [**createCompetitor**](docs/CompetitorsApi.md#createcompetitoroperation) | **POST** /competitors | Add a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor
*CompetitorsApi* | [**getCompetitorDetails**](docs/CompetitorsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details
*CompetitorsApi* | [**listCompetitors**](docs/CompetitorsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors
*CompetitorsApi* | [**updateCompetitor**](docs/CompetitorsApi.md#updatecompetitoroperation) | **PATCH** /competitors/{id} | Update a competitor
*GEOWriterApi* | [**createIntelligenceTask**](docs/GEOWriterApi.md#createintelligencetask) | **POST** /intelligence_tasks | Create a GEO Writer task
*GEOWriterApi* | [**getIntelligenceTask**](docs/GEOWriterApi.md#getintelligencetask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task
*GEOWriterApi* | [**listIntelligenceTasks**](docs/GEOWriterApi.md#listintelligencetasks) | **GET** /intelligence_tasks | List GEO Writer tasks
*GEOWriterApi* | [**revertIntelligenceTaskContent**](docs/GEOWriterApi.md#revertintelligencetaskcontent) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content
*GEOWriterApi* | [**updateIntelligenceTaskContent**](docs/GEOWriterApi.md#updateintelligencetaskcontent) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content
*HealthApi* | [**ping**](docs/HealthApi.md#ping) | **GET** /ping | Health check
*MentionsCitationsApi* | [**listAllCitations**](docs/MentionsCitationsApi.md#listallcitations) | **GET** /dimensions/all_citations | List all citations (brand + competitor)
*MentionsCitationsApi* | [**listAllMentions**](docs/MentionsCitationsApi.md#listallmentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor)
*MentionsCitationsApi* | [**listCitations**](docs/MentionsCitationsApi.md#listcitations) | **GET** /dimensions/citations | List brand citations
*MentionsCitationsApi* | [**listCompetitorCitations**](docs/MentionsCitationsApi.md#listcompetitorcitations) | **GET** /dimensions/competitor_citations | List competitor citations
*MentionsCitationsApi* | [**listCompetitorMentions**](docs/MentionsCitationsApi.md#listcompetitormentions) | **GET** /dimensions/competitor_mentions | List competitor mentions
*MentionsCitationsApi* | [**listMentions**](docs/MentionsCitationsApi.md#listmentions) | **GET** /dimensions/mentions | List brand mentions
*MetricsApi* | [**getPromptSummary**](docs/MetricsApi.md#getpromptsummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary
*MetricsApi* | [**getShareOfVoice**](docs/MetricsApi.md#getshareofvoice) | **GET** /metrics/sov | Share of Voice
*MetricsApi* | [**getSummary**](docs/MetricsApi.md#getsummary) | **GET** /metrics/summary | Aggregated metrics summary
*MetricsApi* | [**getTimeseries**](docs/MetricsApi.md#gettimeseries) | **GET** /metrics/timeseries | Time-series metrics
*MetricsApi* | [**getTopSources**](docs/MetricsApi.md#gettopsources) | **GET** /metrics/top_sources | Top cited sources
*OwnedMediaCommunitiesApi* | [**listOwnedMedia**](docs/OwnedMediaCommunitiesApi.md#listownedmedia) | **GET** /dimensions/owned_media | List owned-media citations
*OwnedMediaCommunitiesApi* | [**listRedditCitations**](docs/OwnedMediaCommunitiesApi.md#listredditcitations) | **GET** /dimensions/reddit | List cited Reddit content
*ProjectsApi* | [**createProject**](docs/ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode)
*ProjectsApi* | [**createProjectDraft**](docs/ProjectsApi.md#createprojectdraftoperation) | **POST** /project_drafts | Start a project draft (wizard step 1)
*ProjectsApi* | [**finalizeProjectDraft**](docs/ProjectsApi.md#finalizeprojectdraftoperation) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project
*ProjectsApi* | [**getProjectDetails**](docs/ProjectsApi.md#getprojectdetails) | **GET** /dimensions/projects/{id} | Project details
*ProjectsApi* | [**getProjectDraft**](docs/ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft
*ProjectsApi* | [**listLocales**](docs/ProjectsApi.md#listlocales) | **GET** /dimensions/locales | List locales with data
*ProjectsApi* | [**listModels**](docs/ProjectsApi.md#listmodels) | **GET** /dimensions/models | List models with data
*ProjectsApi* | [**listProjects**](docs/ProjectsApi.md#listprojects) | **GET** /dimensions/projects | List projects
*ProjectsApi* | [**updateProject**](docs/ProjectsApi.md#updateprojectoperation) | **PATCH** /projects/{id} | Update a project profile (Brand Book)
*ProjectsApi* | [**updateProjectDraft**](docs/ProjectsApi.md#updateprojectdraftoperation) | **PATCH** /project_drafts/{id} | Submit a wizard step
*PromptsApi* | [**createPrompts**](docs/PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts
*PromptsApi* | [**deletePrompt**](docs/PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt
*PromptsApi* | [**listPromptExecutions**](docs/PromptsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions
*PromptsApi* | [**listPrompts**](docs/PromptsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts
*PromptsApi* | [**listQueryFanOuts**](docs/PromptsApi.md#listqueryfanouts) | **GET** /dimensions/query_fan_outs | List query fan-out
*RecommendationsApi* | [**getRecommendation**](docs/RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items
*RecommendationsApi* | [**launchRecommendations**](docs/RecommendationsApi.md#launchrecommendationsoperation) | **POST** /recommendations | Launch a recommendations generation
*RecommendationsApi* | [**listRecommendations**](docs/RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs
*ReputationStudiesApi* | [**getReputationReport**](docs/ReputationStudiesApi.md#getreputationreport) | **GET** /reputation/reports/{id} | Get reputation report scores
*ReputationStudiesApi* | [**getStudy**](docs/ReputationStudiesApi.md#getstudy) | **GET** /studies/{id} | Get a custom AI study
*ReputationStudiesApi* | [**getStudyReport**](docs/ReputationStudiesApi.md#getstudyreport) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores
*ReputationStudiesApi* | [**listReputationReports**](docs/ReputationStudiesApi.md#listreputationreports) | **GET** /reputation/reports | List reputation reports
*ReputationStudiesApi* | [**listStudies**](docs/ReputationStudiesApi.md#liststudies) | **GET** /studies | List custom AI studies
*SearchConsoleApi* | [**getSearchConsolePages**](docs/SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+)
*SearchConsoleApi* | [**getSearchConsoleQueries**](docs/SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+)
*SearchConsoleApi* | [**getSearchConsoleSummary**](docs/SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+)
*SearchConsoleApi* | [**getSearchConsoleTimeseries**](docs/SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+)
*SentimentsApi* | [**listSentimentCategories**](docs/SentimentsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories
*SentimentsApi* | [**listSentimentRecords**](docs/SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records
*ShoppingAdsApi* | [**listAds**](docs/ShoppingAdsApi.md#listads) | **GET** /dimensions/ads | List AI ad placements
*ShoppingAdsApi* | [**listShopping**](docs/ShoppingAdsApi.md#listshopping) | **GET** /dimensions/shopping | List shopping results
*SourcesCitationIntelligenceApi* | [**getCitedUrlContent**](docs/SourcesCitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content
*SourcesCitationIntelligenceApi* | [**getCitedUrlDetail**](docs/SourcesCitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail
*SourcesCitationIntelligenceApi* | [**getMentionsByCitingDomain**](docs/SourcesCitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain
*SourcesCitationIntelligenceApi* | [**listCitationGroups**](docs/SourcesCitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence
*SourcesCitationIntelligenceApi* | [**listCitedUrlOccurrences**](docs/SourcesCitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences
*SourcesCitationIntelligenceApi* | [**listSources**](docs/SourcesCitationIntelligenceApi.md#listsources) | **GET** /dimensions/sources | List source URLs
*TechnicalGEOReportsApi* | [**createTechnicalGeoReports**](docs/TechnicalGEOReportsApi.md#createtechnicalgeoreportsoperation) | **POST** /technical_geo_reports | Run technical GEO analysis
*TechnicalGEOReportsApi* | [**getTechnicalGeoReport**](docs/TechnicalGEOReportsApi.md#gettechnicalgeoreport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report
*TechnicalGEOReportsApi* | [**listTechnicalGeoReports**](docs/TechnicalGEOReportsApi.md#listtechnicalgeoreports) | **GET** /technical_geo_reports | List technical GEO reports
*WebhooksApi* | [**createWebhook**](docs/WebhooksApi.md#createwebhookoperation) | **POST** /webhooks | Create a webhook subscription
*WebhooksApi* | [**deleteWebhook**](docs/WebhooksApi.md#deletewebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription
*WebhooksApi* | [**listWebhooks**](docs/WebhooksApi.md#listwebhooks) | **GET** /webhooks | List webhook subscriptions
*WebhooksApi* | [**sampleWebhookPayloads**](docs/WebhooksApi.md#samplewebhookpayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads


### Models

- [AccountCapacity](docs/AccountCapacity.md)
- [AccountQuota](docs/AccountQuota.md)
- [Actor](docs/Actor.md)
- [AgentBot](docs/AgentBot.md)
- [AgentBotsResponse](docs/AgentBotsResponse.md)
- [AgentTrafficResponse](docs/AgentTrafficResponse.md)
- [AnswerDetails](docs/AnswerDetails.md)
- [AnswerDetailsLocale](docs/AnswerDetailsLocale.md)
- [ApiError](docs/ApiError.md)
- [ApiErrorError](docs/ApiErrorError.md)
- [AssignPromptTagsRequest](docs/AssignPromptTagsRequest.md)
- [Competitor](docs/Competitor.md)
- [CompetitorDetails](docs/CompetitorDetails.md)
- [CreateAnnotationRequest](docs/CreateAnnotationRequest.md)
- [CreateCollectionRequest](docs/CreateCollectionRequest.md)
- [CreateCompetitorRequest](docs/CreateCompetitorRequest.md)
- [CreateProjectDraftRequest](docs/CreateProjectDraftRequest.md)
- [CreateTechnicalGeoReportsRequest](docs/CreateTechnicalGeoReportsRequest.md)
- [CreateWebhook201Response](docs/CreateWebhook201Response.md)
- [CreateWebhookRequest](docs/CreateWebhookRequest.md)
- [DeleteWebhook200Response](docs/DeleteWebhook200Response.md)
- [FinalizeProjectDraftRequest](docs/FinalizeProjectDraftRequest.md)
- [GetAccount200Response](docs/GetAccount200Response.md)
- [GetAccount200ResponseLimits](docs/GetAccount200ResponseLimits.md)
- [GetAccount200ResponseRateLimits](docs/GetAccount200ResponseRateLimits.md)
- [GetAccount200ResponseSubscription](docs/GetAccount200ResponseSubscription.md)
- [IntelligenceTask](docs/IntelligenceTask.md)
- [IntelligenceTaskCreateRequest](docs/IntelligenceTaskCreateRequest.md)
- [IntelligenceTaskUpdateRequest](docs/IntelligenceTaskUpdateRequest.md)
- [IntelligenceTaskUpdateResponse](docs/IntelligenceTaskUpdateResponse.md)
- [LaunchRecommendationsRequest](docs/LaunchRecommendationsRequest.md)
- [ListCompetitors200Response](docs/ListCompetitors200Response.md)
- [ListProjects200Response](docs/ListProjects200Response.md)
- [ListWebhooks200Response](docs/ListWebhooks200Response.md)
- [ListWebhooks200ResponseDataInner](docs/ListWebhooks200ResponseDataInner.md)
- [Ping200Response](docs/Ping200Response.md)
- [Project](docs/Project.md)
- [ProjectCreateRequest](docs/ProjectCreateRequest.md)
- [ProjectCreateRequestCompetitorsInner](docs/ProjectCreateRequestCompetitorsInner.md)
- [ProjectCreateRequestOwnedMedia](docs/ProjectCreateRequestOwnedMedia.md)
- [ProjectCreateResponse](docs/ProjectCreateResponse.md)
- [ProjectCreateResponseCompetitors](docs/ProjectCreateResponseCompetitors.md)
- [ProjectCreateResponseEmailSubscription](docs/ProjectCreateResponseEmailSubscription.md)
- [ProjectCreateResponseLimits](docs/ProjectCreateResponseLimits.md)
- [ProjectCreateResponsePrompts](docs/ProjectCreateResponsePrompts.md)
- [ProjectDetails](docs/ProjectDetails.md)
- [ProjectDetailsAllOfStats](docs/ProjectDetailsAllOfStats.md)
- [PromptSummaryResponse](docs/PromptSummaryResponse.md)
- [PromptSummaryRow](docs/PromptSummaryRow.md)
- [PromptsCreateRequest](docs/PromptsCreateRequest.md)
- [PromptsCreateResponse](docs/PromptsCreateResponse.md)
- [PromptsCreateResponseDataInner](docs/PromptsCreateResponseDataInner.md)
- [SampleWebhookPayloads200Response](docs/SampleWebhookPayloads200Response.md)
- [SampleWebhookPayloads200ResponseDataInner](docs/SampleWebhookPayloads200ResponseDataInner.md)
- [SearchConsoleFiltersInner](docs/SearchConsoleFiltersInner.md)
- [SovResponse](docs/SovResponse.md)
- [SovResponseBreakdownInner](docs/SovResponseBreakdownInner.md)
- [SovResponseCurrentInner](docs/SovResponseCurrentInner.md)
- [SovResponseOverTimeInner](docs/SovResponseOverTimeInner.md)
- [SovResponsePeriodsInner](docs/SovResponsePeriodsInner.md)
- [SummaryResponse](docs/SummaryResponse.md)
- [SummaryResponseAllOfPositionDistribution](docs/SummaryResponseAllOfPositionDistribution.md)
- [SummaryResponseAllOfSummaryValueInner](docs/SummaryResponseAllOfSummaryValueInner.md)
- [TimeseriesPoint](docs/TimeseriesPoint.md)
- [TimeseriesResponse](docs/TimeseriesResponse.md)
- [TimeseriesSeries](docs/TimeseriesSeries.md)
- [TopSourcesResponse](docs/TopSourcesResponse.md)
- [TopSourcesResponseDataInner](docs/TopSourcesResponseDataInner.md)
- [UpdateAnnotationRequest](docs/UpdateAnnotationRequest.md)
- [UpdateCollectionRequest](docs/UpdateCollectionRequest.md)
- [UpdateCompetitorRequest](docs/UpdateCompetitorRequest.md)
- [UpdateProjectDraftRequest](docs/UpdateProjectDraftRequest.md)
- [UpdateProjectRequest](docs/UpdateProjectRequest.md)

### Authorization


Authentication schemes defined for the API:
<a id="BearerAuth"></a>
#### BearerAuth


- **Type**: HTTP Bearer Token authentication

## About

This TypeScript SDK client supports the [Fetch API](https://fetch.spec.whatwg.org/)
and is automatically generated by the
[OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.48.0`
- Package version: `1.48.0`
- Generator version: `7.24.0`
- Build package: `org.openapitools.codegen.languages.TypeScriptFetchClientCodegen`

The generated npm module supports the following:

- Environments
  * Node.js
  * Webpack
  * Browserify
- Language levels
  * ES5 - you must have a Promises/A+ library installed
  * ES6
- Module systems
  * CommonJS
  * ES6 module system

For more information, please visit [https://llmpulse.ai](https://llmpulse.ai)

## Development

### Building

To build the TypeScript source code, you need to have Node.js and npm installed.
After cloning the repository, navigate to the project directory and run:

```bash
npm install
npm run build
```

### Publishing

Once you've built the package, you can publish it to npm:

```bash
npm publish
```

## License

[MIT](https://opensource.org/license/mit)
