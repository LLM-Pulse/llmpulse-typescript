# @llmpulse/sdk@1.22.0

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
  AIModelInsightsApi,
} from '@llmpulse/sdk';
import type { GetAiModelInsightsSummaryRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIModelInsightsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
    // number (optional)
    collectionId: 56,
    // string | ISO country code (e.g. US, GB, DE) (optional)
    countryCode: countryCode_example,
    // string | ISO language code (e.g. en, es, de) (optional)
    languageCode: languageCode_example,
    // 'informational' | 'navigational' | 'commercial' | 'transactional' | Filter by prompt type (search intent) (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
  } satisfies GetAiModelInsightsSummaryRequest;

  try {
    const data = await api.getAiModelInsightsSummary(body);
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
*AIModelInsightsApi* | [**getAiModelInsightsSummary**](docs/AIModelInsightsApi.md#getaimodelinsightssummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary
*AIModelInsightsApi* | [**getAiModelPositionDistribution**](docs/AIModelInsightsApi.md#getaimodelpositiondistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison
*AIModelInsightsApi* | [**getAiOverviewResults**](docs/AIModelInsightsApi.md#getaioverviewresults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability
*AnnotationsApi* | [**createAnnotation**](docs/AnnotationsApi.md#createannotationoperation) | **POST** /annotations | Create a timeline annotation
*AnnotationsApi* | [**deleteAnnotation**](docs/AnnotationsApi.md#deleteannotation) | **DELETE** /annotations/{id} | Delete a timeline annotation
*AnnotationsApi* | [**listAnnotations**](docs/AnnotationsApi.md#listannotations) | **GET** /annotations | List timeline annotations
*AnnotationsApi* | [**updateAnnotation**](docs/AnnotationsApi.md#updateannotationoperation) | **PATCH** /annotations/{id} | Update a timeline annotation
*AnswersApi* | [**getAnswer**](docs/AnswersApi.md#getanswer) | **GET** /answers/{id} | Get one AI response
*AnswersApi* | [**listAnswers**](docs/AnswersApi.md#listanswers) | **GET** /answers | List AI responses
*CitationIntelligenceApi* | [**getCitedUrlContent**](docs/CitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content
*CitationIntelligenceApi* | [**getCitedUrlDetail**](docs/CitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail
*CitationIntelligenceApi* | [**getMentionsByCitingDomain**](docs/CitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain
*CitationIntelligenceApi* | [**listCitationGroups**](docs/CitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence
*CitationIntelligenceApi* | [**listCitedUrlOccurrences**](docs/CitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences
*CollectionsApi* | [**createCollection**](docs/CollectionsApi.md#createcollectionoperation) | **POST** /collections | Create a tag
*CollectionsApi* | [**deleteCollection**](docs/CollectionsApi.md#deletecollection) | **DELETE** /collections/{id} | Delete a tag
*CollectionsApi* | [**updateCollection**](docs/CollectionsApi.md#updatecollectionoperation) | **PATCH** /collections/{id} | Update a tag
*CompetitorsApi* | [**createCompetitor**](docs/CompetitorsApi.md#createcompetitoroperation) | **POST** /competitors | Add a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor
*CompetitorsApi* | [**updateCompetitor**](docs/CompetitorsApi.md#updatecompetitoroperation) | **PATCH** /competitors/{id} | Update a competitor
*DimensionsApi* | [**getCompetitorDetails**](docs/DimensionsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details
*DimensionsApi* | [**getProjectDetails**](docs/DimensionsApi.md#getprojectdetails) | **GET** /dimensions/projects/{id} | Project details
*DimensionsApi* | [**listAgentBots**](docs/DimensionsApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale+)
*DimensionsApi* | [**listAllCitations**](docs/DimensionsApi.md#listallcitations) | **GET** /dimensions/all_citations | List all citations (brand + competitor)
*DimensionsApi* | [**listAllMentions**](docs/DimensionsApi.md#listallmentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor)
*DimensionsApi* | [**listCitations**](docs/DimensionsApi.md#listcitations) | **GET** /dimensions/citations | List brand citations
*DimensionsApi* | [**listCollections**](docs/DimensionsApi.md#listcollections) | **GET** /dimensions/collections | List tags/collections
*DimensionsApi* | [**listCompetitorCitations**](docs/DimensionsApi.md#listcompetitorcitations) | **GET** /dimensions/competitor_citations | List competitor citations
*DimensionsApi* | [**listCompetitorMentions**](docs/DimensionsApi.md#listcompetitormentions) | **GET** /dimensions/competitor_mentions | List competitor mentions
*DimensionsApi* | [**listCompetitors**](docs/DimensionsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors
*DimensionsApi* | [**listLocales**](docs/DimensionsApi.md#listlocales) | **GET** /dimensions/locales | List locales with data
*DimensionsApi* | [**listMentions**](docs/DimensionsApi.md#listmentions) | **GET** /dimensions/mentions | List brand mentions
*DimensionsApi* | [**listModels**](docs/DimensionsApi.md#listmodels) | **GET** /dimensions/models | List models with data
*DimensionsApi* | [**listProjects**](docs/DimensionsApi.md#listprojects) | **GET** /dimensions/projects | List projects
*DimensionsApi* | [**listPromptExecutions**](docs/DimensionsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions
*DimensionsApi* | [**listPrompts**](docs/DimensionsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts
*DimensionsApi* | [**listSentimentCategories**](docs/DimensionsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories
*DimensionsApi* | [**listSources**](docs/DimensionsApi.md#listsources) | **GET** /dimensions/sources | List source URLs
*DimensionsApi* | [**listTags**](docs/DimensionsApi.md#listtags) | **GET** /dimensions/tags | List tags (alias for /collections)
*GEOWriterApi* | [**createIntelligenceTask**](docs/GEOWriterApi.md#createintelligencetask) | **POST** /intelligence_tasks | Create a GEO Writer task
*GEOWriterApi* | [**getIntelligenceTask**](docs/GEOWriterApi.md#getintelligencetask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task
*GEOWriterApi* | [**listIntelligenceTasks**](docs/GEOWriterApi.md#listintelligencetasks) | **GET** /intelligence_tasks | List GEO Writer tasks
*HealthApi* | [**ping**](docs/HealthApi.md#ping) | **GET** /ping | Health check
*MetricsApi* | [**getAgentTraffic**](docs/MetricsApi.md#getagenttraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale+, Beta)
*MetricsApi* | [**getAiTraffic**](docs/MetricsApi.md#getaitraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale+)
*MetricsApi* | [**getPromptSummary**](docs/MetricsApi.md#getpromptsummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary
*MetricsApi* | [**getShareOfVoice**](docs/MetricsApi.md#getshareofvoice) | **GET** /metrics/sov | Share of Voice
*MetricsApi* | [**getSummary**](docs/MetricsApi.md#getsummary) | **GET** /metrics/summary | Aggregated metrics summary
*MetricsApi* | [**getTimeseries**](docs/MetricsApi.md#gettimeseries) | **GET** /metrics/timeseries | Time-series metrics
*MetricsApi* | [**getTopSources**](docs/MetricsApi.md#gettopsources) | **GET** /metrics/top_sources | Top cited sources
*ProjectsApi* | [**createProject**](docs/ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode)
*ProjectsApi* | [**createProjectDraft**](docs/ProjectsApi.md#createprojectdraftoperation) | **POST** /project_drafts | Start a project draft (wizard step 1)
*ProjectsApi* | [**finalizeProjectDraft**](docs/ProjectsApi.md#finalizeprojectdraftoperation) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project
*ProjectsApi* | [**getProjectDraft**](docs/ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft
*ProjectsApi* | [**updateProjectDraft**](docs/ProjectsApi.md#updateprojectdraftoperation) | **PATCH** /project_drafts/{id} | Submit a wizard step
*PromptsApi* | [**assignPromptTags**](docs/PromptsApi.md#assignprompttagsoperation) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts
*PromptsApi* | [**createPrompts**](docs/PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts
*PromptsApi* | [**deletePrompt**](docs/PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt
*RecommendationsApi* | [**getRecommendation**](docs/RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items
*RecommendationsApi* | [**launchRecommendations**](docs/RecommendationsApi.md#launchrecommendationsoperation) | **POST** /recommendations | Launch a recommendations generation
*RecommendationsApi* | [**listRecommendations**](docs/RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs
*ReportsApi* | [**createTechnicalGeoReports**](docs/ReportsApi.md#createtechnicalgeoreportsoperation) | **POST** /technical_geo_reports | Run technical GEO analysis
*SearchConsoleApi* | [**getSearchConsolePages**](docs/SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+)
*SearchConsoleApi* | [**getSearchConsoleQueries**](docs/SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+)
*SearchConsoleApi* | [**getSearchConsoleSummary**](docs/SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+)
*SearchConsoleApi* | [**getSearchConsoleTimeseries**](docs/SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+)
*SentimentsApi* | [**listSentimentRecords**](docs/SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records
*WebhooksApi* | [**createWebhook**](docs/WebhooksApi.md#createwebhookoperation) | **POST** /webhooks | Create a webhook subscription
*WebhooksApi* | [**deleteWebhook**](docs/WebhooksApi.md#deletewebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription
*WebhooksApi* | [**listWebhooks**](docs/WebhooksApi.md#listwebhooks) | **GET** /webhooks | List webhook subscriptions
*WebhooksApi* | [**sampleWebhookPayloads**](docs/WebhooksApi.md#samplewebhookpayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads


### Models

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
- [IntelligenceTask](docs/IntelligenceTask.md)
- [IntelligenceTaskCreateRequest](docs/IntelligenceTaskCreateRequest.md)
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

### Authorization


Authentication schemes defined for the API:
<a id="BearerAuth"></a>
#### BearerAuth


- **Type**: HTTP Bearer Token authentication

## About

This TypeScript SDK client supports the [Fetch API](https://fetch.spec.whatwg.org/)
and is automatically generated by the
[OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.22.0`
- Package version: `1.22.0`
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
