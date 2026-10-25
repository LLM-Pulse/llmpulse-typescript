# @llmpulse/sdk@1.71.0

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
*AIAgentTrafficApi* | [**getWebAnalyticsSchema**](docs/AIAgentTrafficApi.md#getwebanalyticsschema) | **GET** /web_analytics/schema | Web analytics query format (Growth+)
*AIAgentTrafficApi* | [**listAgentBots**](docs/AIAgentTrafficApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above)
*AIAgentTrafficApi* | [**queryWebAnalytics**](docs/AIAgentTrafficApi.md#querywebanalyticsoperation) | **POST** /web_analytics/query | Live web analytics query (Growth+)
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
*CollectionsTagsApi* | [**removePromptTags**](docs/CollectionsTagsApi.md#removeprompttagsoperation) | **POST** /prompts/remove_tags | Bulk-detach tags from prompts
*CollectionsTagsApi* | [**updateCollection**](docs/CollectionsTagsApi.md#updatecollectionoperation) | **PATCH** /collections/{id} | Update a tag
*CompetitorsApi* | [**createCompetitor**](docs/CompetitorsApi.md#createcompetitoroperation) | **POST** /competitors | Add a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor
*CompetitorsApi* | [**getCompetitorDetails**](docs/CompetitorsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details
*CompetitorsApi* | [**listCompetitorSuggestions**](docs/CompetitorsApi.md#listcompetitorsuggestions) | **GET** /competitors/suggestions | List competitor suggestions
*CompetitorsApi* | [**listCompetitors**](docs/CompetitorsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors
*CompetitorsApi* | [**updateCompetitor**](docs/CompetitorsApi.md#updatecompetitoroperation) | **PATCH** /competitors/{id} | Update a competitor
*CustomReportsApi* | [**getCustomReport**](docs/CustomReportsApi.md#getcustomreport) | **GET** /custom_reports/{id} | Get a custom report with its widget data
*CustomReportsApi* | [**listCustomReports**](docs/CustomReportsApi.md#listcustomreports) | **GET** /custom_reports | List custom reports
*CustomReportsApi* | [**sendCustomReport**](docs/CustomReportsApi.md#sendcustomreportoperation) | **POST** /custom_reports/{id}/send | Send a custom report now
*GEOAuditsApi* | [**compareGeoAuditRuns**](docs/GEOAuditsApi.md#comparegeoauditruns) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs
*GEOAuditsApi* | [**createGeoAudits**](docs/GEOAuditsApi.md#creategeoaudits) | **POST** /geo_audits | Create GEO audits
*GEOAuditsApi* | [**deleteGeoAudit**](docs/GEOAuditsApi.md#deletegeoaudit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit
*GEOAuditsApi* | [**getGeoAudit**](docs/GEOAuditsApi.md#getgeoaudit) | **GET** /geo_audits/{id} | Get a GEO audit
*GEOAuditsApi* | [**getGeoAuditRun**](docs/GEOAuditsApi.md#getgeoauditrun) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run
*GEOAuditsApi* | [**listGeoAlerts**](docs/GEOAuditsApi.md#listgeoalerts) | **GET** /geo_alerts | List GEO audit alerts
*GEOAuditsApi* | [**listGeoAuditFindings**](docs/GEOAuditsApi.md#listgeoauditfindings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run
*GEOAuditsApi* | [**listGeoAuditIssues**](docs/GEOAuditsApi.md#listgeoauditissues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit
*GEOAuditsApi* | [**listGeoAuditRuns**](docs/GEOAuditsApi.md#listgeoauditruns) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit
*GEOAuditsApi* | [**listGeoAudits**](docs/GEOAuditsApi.md#listgeoaudits) | **GET** /geo_audits | List GEO audits
*GEOAuditsApi* | [**runGeoAudit**](docs/GEOAuditsApi.md#rungeoaudit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now
*GEOAuditsApi* | [**updateGeoAudit**](docs/GEOAuditsApi.md#updategeoaudit) | **PATCH** /geo_audits/{id} | Update a GEO audit
*GEOAuditsApi* | [**updateGeoAuditIssue**](docs/GEOAuditsApi.md#updategeoauditissue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue
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
*OwnedMediaCommunitiesApi* | [**getOwnedMediaProfiles**](docs/OwnedMediaCommunitiesApi.md#getownedmediaprofiles) | **GET** /projects/{id}/owned_media | Get a project\&#39;s owned-media profiles
*OwnedMediaCommunitiesApi* | [**getOwnedMediaSummary**](docs/OwnedMediaCommunitiesApi.md#getownedmediasummary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary
*OwnedMediaCommunitiesApi* | [**listOwnedMedia**](docs/OwnedMediaCommunitiesApi.md#listownedmedia) | **GET** /dimensions/owned_media | List owned-media citations
*OwnedMediaCommunitiesApi* | [**listOwnedMediaCitingPrompts**](docs/OwnedMediaCommunitiesApi.md#listownedmediacitingprompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item
*OwnedMediaCommunitiesApi* | [**listRedditCitations**](docs/OwnedMediaCommunitiesApi.md#listredditcitations) | **GET** /dimensions/reddit | List cited Reddit content
*OwnedMediaCommunitiesApi* | [**updateOwnedMediaProfiles**](docs/OwnedMediaCommunitiesApi.md#updateownedmediaprofilesoperation) | **PATCH** /projects/{id}/owned_media | Update a project\&#39;s owned-media profiles
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
*PromptsApi* | [**acceptSuggestedPrompts**](docs/PromptsApi.md#acceptsuggestedprompts) | **POST** /suggested_prompts/accept | Accept suggested prompts
*PromptsApi* | [**createPromptGeneration**](docs/PromptsApi.md#createpromptgeneration) | **POST** /prompt_generations | Generate prompt suggestions
*PromptsApi* | [**createPrompts**](docs/PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts
*PromptsApi* | [**deletePrompt**](docs/PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt
*PromptsApi* | [**getPromptGeneration**](docs/PromptsApi.md#getpromptgeneration) | **GET** /prompt_generations/{id} | Get a prompt generation run
*PromptsApi* | [**importPrompts**](docs/PromptsApi.md#importprompts) | **POST** /prompts/import | Import prompts
*PromptsApi* | [**listPromptExecutions**](docs/PromptsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions
*PromptsApi* | [**listPrompts**](docs/PromptsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts
*PromptsApi* | [**listQueryFanOuts**](docs/PromptsApi.md#listqueryfanouts) | **GET** /dimensions/query_fan_outs | List query fan-out
*PromptsApi* | [**listSuggestedPrompts**](docs/PromptsApi.md#listsuggestedprompts) | **GET** /suggested_prompts | List suggested prompts
*PromptsApi* | [**rejectSuggestedPrompts**](docs/PromptsApi.md#rejectsuggestedprompts) | **POST** /suggested_prompts/reject | Reject suggested prompts
*PromptsApi* | [**updatePrompt**](docs/PromptsApi.md#updatepromptoperation) | **PATCH** /prompts/{id} | Edit a prompt\&#39;s categorization
*RecommendationsApi* | [**getRecommendation**](docs/RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items
*RecommendationsApi* | [**launchRecommendations**](docs/RecommendationsApi.md#launchrecommendationsoperation) | **POST** /recommendations | Launch a recommendations generation
*RecommendationsApi* | [**listRecommendations**](docs/RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs
*RecommendationsApi* | [**updateRecommendationItem**](docs/RecommendationsApi.md#updaterecommendationitemoperation) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item
*ReputationStudiesApi* | [**getReputationReport**](docs/ReputationStudiesApi.md#getreputationreport) | **GET** /reputation/reports/{id} | Get reputation report scores
*ReputationStudiesApi* | [**getStudy**](docs/ReputationStudiesApi.md#getstudy) | **GET** /studies/{id} | Get a custom AI study
*ReputationStudiesApi* | [**getStudyReport**](docs/ReputationStudiesApi.md#getstudyreport) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores
*ReputationStudiesApi* | [**listReputationReports**](docs/ReputationStudiesApi.md#listreputationreports) | **GET** /reputation/reports | List reputation reports
*ReputationStudiesApi* | [**listStudies**](docs/ReputationStudiesApi.md#liststudies) | **GET** /studies | List custom AI studies
*SearchConsoleApi* | [**getSearchConsolePages**](docs/SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+)
*SearchConsoleApi* | [**getSearchConsoleQueries**](docs/SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+)
*SearchConsoleApi* | [**getSearchConsoleRows**](docs/SearchConsoleApi.md#getsearchconsolerows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+)
*SearchConsoleApi* | [**getSearchConsoleSummary**](docs/SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+)
*SearchConsoleApi* | [**getSearchConsoleTimeseries**](docs/SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+)
*SearchConsoleApi* | [**listSearchConsoleProperties**](docs/SearchConsoleApi.md#listsearchconsoleproperties) | **GET** /search_console/properties | List Search Console properties (Growth+)
*SentimentsApi* | [**getSentimentTags**](docs/SentimentsApi.md#getsentimenttags) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above)
*SentimentsApi* | [**getSentimentTopics**](docs/SentimentsApi.md#getsentimenttopics) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above)
*SentimentsApi* | [**listSentimentCategories**](docs/SentimentsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above)
*SentimentsApi* | [**listSentimentRecords**](docs/SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records (Growth plan or above)
*ShoppingAdsApi* | [**listAds**](docs/ShoppingAdsApi.md#listads) | **GET** /dimensions/ads | List AI ad placements
*ShoppingAdsApi* | [**listLocalBusinesses**](docs/ShoppingAdsApi.md#listlocalbusinesses) | **GET** /dimensions/local_businesses | List local businesses
*ShoppingAdsApi* | [**listShopping**](docs/ShoppingAdsApi.md#listshopping) | **GET** /dimensions/shopping | List shopping results
*SourcesCitationIntelligenceApi* | [**getCitedUrlContent**](docs/SourcesCitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content
*SourcesCitationIntelligenceApi* | [**getCitedUrlDetail**](docs/SourcesCitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail
*SourcesCitationIntelligenceApi* | [**getMentionsByCitingDomain**](docs/SourcesCitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain
*SourcesCitationIntelligenceApi* | [**listCitationGroups**](docs/SourcesCitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence
*SourcesCitationIntelligenceApi* | [**listCitedUrlOccurrences**](docs/SourcesCitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences
*SourcesCitationIntelligenceApi* | [**listSources**](docs/SourcesCitationIntelligenceApi.md#listsources) | **GET** /dimensions/sources | List source URLs
*StoreIntegrationsApi* | [**acceptCatalogPromptSuggestions**](docs/StoreIntegrationsApi.md#acceptcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions
*StoreIntegrationsApi* | [**createCatalogPromptSuggestions**](docs/StoreIntegrationsApi.md#createcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products
*StoreIntegrationsApi* | [**getStoreConnection**](docs/StoreIntegrationsApi.md#getstoreconnection) | **GET** /store_connection | Match a store to a project
*StoreIntegrationsApi* | [**listAiOrders**](docs/StoreIntegrationsApi.md#listaiorders) | **GET** /ai_orders | Read AI-referred store orders
*StoreIntegrationsApi* | [**listCatalogPromptSuggestions**](docs/StoreIntegrationsApi.md#listcatalogpromptsuggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions
*StoreIntegrationsApi* | [**rejectCatalogPromptSuggestions**](docs/StoreIntegrationsApi.md#rejectcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions
*StoreIntegrationsApi* | [**replaceAiOrders**](docs/StoreIntegrationsApi.md#replaceaiorders) | **PUT** /ai_orders | Replace AI-referred store orders for a window
*TeamApi* | [**createTeamInvitation**](docs/TeamApi.md#createteaminvitationoperation) | **POST** /team_invitations | Invite a team member
*TeamApi* | [**listTeamInvitations**](docs/TeamApi.md#listteaminvitations) | **GET** /team_invitations | List pending team invitations
*TeamApi* | [**listTeamMembers**](docs/TeamApi.md#listteammembers) | **GET** /team_members | List team members
*TeamApi* | [**removeTeamMember**](docs/TeamApi.md#removeteammember) | **DELETE** /team_members/{id} | Remove a team member
*TeamApi* | [**revokeTeamInvitation**](docs/TeamApi.md#revoketeaminvitation) | **DELETE** /team_invitations/{id} | Revoke a pending team invitation
*TechnicalGEOReportsApi* | [**createTechnicalGeoReports**](docs/TechnicalGEOReportsApi.md#createtechnicalgeoreportsoperation) | **POST** /technical_geo_reports | Run technical GEO analysis
*TechnicalGEOReportsApi* | [**getTechnicalGeoReport**](docs/TechnicalGEOReportsApi.md#gettechnicalgeoreport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report
*TechnicalGEOReportsApi* | [**listTechnicalGeoReports**](docs/TechnicalGEOReportsApi.md#listtechnicalgeoreports) | **GET** /technical_geo_reports | List technical GEO reports
*TechnicalGEOReportsApi* | [**revertTechnicalGeoReportContent**](docs/TechnicalGEOReportsApi.md#reverttechnicalgeoreportcontent) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content
*TechnicalGEOReportsApi* | [**updateTechnicalGeoReportContent**](docs/TechnicalGEOReportsApi.md#updatetechnicalgeoreportcontent) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content
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
- [AiOrdersResponse](docs/AiOrdersResponse.md)
- [AiOrdersResponseBySourceInner](docs/AiOrdersResponseBySourceInner.md)
- [AiOrdersResponseSeriesInner](docs/AiOrdersResponseSeriesInner.md)
- [AiOrdersResponseTotals](docs/AiOrdersResponseTotals.md)
- [AiOrdersUpdateRequest](docs/AiOrdersUpdateRequest.md)
- [AiOrdersUpdateRequestDaysInner](docs/AiOrdersUpdateRequestDaysInner.md)
- [AiOrdersUpdateResponse](docs/AiOrdersUpdateResponse.md)
- [AnnotationCreateResponse](docs/AnnotationCreateResponse.md)
- [AnnotationCreateResponseAnnotation](docs/AnnotationCreateResponseAnnotation.md)
- [AnswerDetails](docs/AnswerDetails.md)
- [AnswerDetailsLocale](docs/AnswerDetailsLocale.md)
- [ApiError](docs/ApiError.md)
- [ApiErrorError](docs/ApiErrorError.md)
- [AssignPromptTagsRequest](docs/AssignPromptTagsRequest.md)
- [CatalogProduct](docs/CatalogProduct.md)
- [CatalogPromptSuggestion](docs/CatalogPromptSuggestion.md)
- [CatalogPromptSuggestionIdsRequest](docs/CatalogPromptSuggestionIdsRequest.md)
- [CatalogPromptSuggestionProduct](docs/CatalogPromptSuggestionProduct.md)
- [CatalogPromptSuggestionsAcceptResponse](docs/CatalogPromptSuggestionsAcceptResponse.md)
- [CatalogPromptSuggestionsAcceptResponseAcceptedInner](docs/CatalogPromptSuggestionsAcceptResponseAcceptedInner.md)
- [CatalogPromptSuggestionsAcceptResponseSkippedInner](docs/CatalogPromptSuggestionsAcceptResponseSkippedInner.md)
- [CatalogPromptSuggestionsCreateRequest](docs/CatalogPromptSuggestionsCreateRequest.md)
- [CatalogPromptSuggestionsCreateResponse](docs/CatalogPromptSuggestionsCreateResponse.md)
- [CatalogPromptSuggestionsRejectResponse](docs/CatalogPromptSuggestionsRejectResponse.md)
- [CatalogPromptSuggestionsResponse](docs/CatalogPromptSuggestionsResponse.md)
- [CitationMatchMode](docs/CitationMatchMode.md)
- [CitationRecord](docs/CitationRecord.md)
- [CitationsResponse](docs/CitationsResponse.md)
- [CollectionCreateResponse](docs/CollectionCreateResponse.md)
- [CollectionCreateResponseCollection](docs/CollectionCreateResponseCollection.md)
- [CollectionsResponse](docs/CollectionsResponse.md)
- [Competitor](docs/Competitor.md)
- [CompetitorCreateResponse](docs/CompetitorCreateResponse.md)
- [CompetitorCreateResponseCompetitor](docs/CompetitorCreateResponseCompetitor.md)
- [CompetitorDetails](docs/CompetitorDetails.md)
- [CompetitorDiscoveryState](docs/CompetitorDiscoveryState.md)
- [CompetitorMentionRecord](docs/CompetitorMentionRecord.md)
- [CompetitorMentionsResponse](docs/CompetitorMentionsResponse.md)
- [CompetitorSuggestion](docs/CompetitorSuggestion.md)
- [CompetitorSuggestionsResponse](docs/CompetitorSuggestionsResponse.md)
- [CreateAnnotationRequest](docs/CreateAnnotationRequest.md)
- [CreateCollectionRequest](docs/CreateCollectionRequest.md)
- [CreateCompetitorRequest](docs/CreateCompetitorRequest.md)
- [CreateProjectDraftRequest](docs/CreateProjectDraftRequest.md)
- [CreateTeamInvitation201Response](docs/CreateTeamInvitation201Response.md)
- [CreateTeamInvitationRequest](docs/CreateTeamInvitationRequest.md)
- [CreateTechnicalGeoReportsRequest](docs/CreateTechnicalGeoReportsRequest.md)
- [CreateWebhook201Response](docs/CreateWebhook201Response.md)
- [CreateWebhookRequest](docs/CreateWebhookRequest.md)
- [CustomReportBlock](docs/CustomReportBlock.md)
- [CustomReportDateRange](docs/CustomReportDateRange.md)
- [CustomReportDetailResponse](docs/CustomReportDetailResponse.md)
- [CustomReportFilters](docs/CustomReportFilters.md)
- [CustomReportSchedule](docs/CustomReportSchedule.md)
- [CustomReportSendResponse](docs/CustomReportSendResponse.md)
- [CustomReportSummary](docs/CustomReportSummary.md)
- [CustomReportWidget](docs/CustomReportWidget.md)
- [CustomReportWidgetRef](docs/CustomReportWidgetRef.md)
- [CustomReportsResponse](docs/CustomReportsResponse.md)
- [DeleteWebhook200Response](docs/DeleteWebhook200Response.md)
- [FinalizeProjectDraftRequest](docs/FinalizeProjectDraftRequest.md)
- [GeoAlert](docs/GeoAlert.md)
- [GeoAlertEventsInner](docs/GeoAlertEventsInner.md)
- [GeoAlertList](docs/GeoAlertList.md)
- [GeoAudit](docs/GeoAudit.md)
- [GeoAuditArchived](docs/GeoAuditArchived.md)
- [GeoAuditComparison](docs/GeoAuditComparison.md)
- [GeoAuditComparisonChangesInner](docs/GeoAuditComparisonChangesInner.md)
- [GeoAuditCreateRequest](docs/GeoAuditCreateRequest.md)
- [GeoAuditCreateResponse](docs/GeoAuditCreateResponse.md)
- [GeoAuditFinding](docs/GeoAuditFinding.md)
- [GeoAuditFindingList](docs/GeoAuditFindingList.md)
- [GeoAuditIssue](docs/GeoAuditIssue.md)
- [GeoAuditIssueList](docs/GeoAuditIssueList.md)
- [GeoAuditIssueResponse](docs/GeoAuditIssueResponse.md)
- [GeoAuditIssueUpdateRequest](docs/GeoAuditIssueUpdateRequest.md)
- [GeoAuditList](docs/GeoAuditList.md)
- [GeoAuditResponse](docs/GeoAuditResponse.md)
- [GeoAuditRun](docs/GeoAuditRun.md)
- [GeoAuditRunDetail](docs/GeoAuditRunDetail.md)
- [GeoAuditRunList](docs/GeoAuditRunList.md)
- [GeoAuditRunResponse](docs/GeoAuditRunResponse.md)
- [GeoAuditSchedule](docs/GeoAuditSchedule.md)
- [GeoAuditUpdateRequest](docs/GeoAuditUpdateRequest.md)
- [GetAccount200Response](docs/GetAccount200Response.md)
- [GetAccount200ResponseLimits](docs/GetAccount200ResponseLimits.md)
- [GetAccount200ResponseRateLimits](docs/GetAccount200ResponseRateLimits.md)
- [GetAccount200ResponseSubscription](docs/GetAccount200ResponseSubscription.md)
- [IntelligenceTask](docs/IntelligenceTask.md)
- [IntelligenceTaskCreateRequest](docs/IntelligenceTaskCreateRequest.md)
- [IntelligenceTaskProduct](docs/IntelligenceTaskProduct.md)
- [IntelligenceTaskProductImagesInner](docs/IntelligenceTaskProductImagesInner.md)
- [IntelligenceTaskSummary](docs/IntelligenceTaskSummary.md)
- [IntelligenceTaskUpdateRequest](docs/IntelligenceTaskUpdateRequest.md)
- [IntelligenceTaskUpdateResponse](docs/IntelligenceTaskUpdateResponse.md)
- [IntelligenceTasksResponse](docs/IntelligenceTasksResponse.md)
- [LaunchRecommendationsRequest](docs/LaunchRecommendationsRequest.md)
- [ListCompetitors200Response](docs/ListCompetitors200Response.md)
- [ListProjects200Response](docs/ListProjects200Response.md)
- [ListTeamInvitations200Response](docs/ListTeamInvitations200Response.md)
- [ListTeamMembers200Response](docs/ListTeamMembers200Response.md)
- [ListWebhooks200Response](docs/ListWebhooks200Response.md)
- [ListWebhooks200ResponseDataInner](docs/ListWebhooks200ResponseDataInner.md)
- [LlmsTxtTechnicalGeoReport](docs/LlmsTxtTechnicalGeoReport.md)
- [LlmsTxtTechnicalGeoReportResultData](docs/LlmsTxtTechnicalGeoReportResultData.md)
- [LocalBusiness](docs/LocalBusiness.md)
- [LocalBusinessesResponse](docs/LocalBusinessesResponse.md)
- [LocalBusinessesTotals](docs/LocalBusinessesTotals.md)
- [LocalesResponse](docs/LocalesResponse.md)
- [MentionRecord](docs/MentionRecord.md)
- [MentionsResponse](docs/MentionsResponse.md)
- [MetricsFiltersEcho](docs/MetricsFiltersEcho.md)
- [ModelsResponse](docs/ModelsResponse.md)
- [OwnedMediaAgeBucketShare](docs/OwnedMediaAgeBucketShare.md)
- [OwnedMediaCitedItem](docs/OwnedMediaCitedItem.md)
- [OwnedMediaCitedItemStats](docs/OwnedMediaCitedItemStats.md)
- [OwnedMediaCitingAnswer](docs/OwnedMediaCitingAnswer.md)
- [OwnedMediaCitingPromptsResponse](docs/OwnedMediaCitingPromptsResponse.md)
- [OwnedMediaContentTypeShare](docs/OwnedMediaContentTypeShare.md)
- [OwnedMediaCountryShare](docs/OwnedMediaCountryShare.md)
- [OwnedMediaKpiChanges](docs/OwnedMediaKpiChanges.md)
- [OwnedMediaKpis](docs/OwnedMediaKpis.md)
- [OwnedMediaListResponse](docs/OwnedMediaListResponse.md)
- [OwnedMediaModelShare](docs/OwnedMediaModelShare.md)
- [OwnedMediaPlatformProfiles](docs/OwnedMediaPlatformProfiles.md)
- [OwnedMediaPlatformRollup](docs/OwnedMediaPlatformRollup.md)
- [OwnedMediaPlatformRollupWeeklyInner](docs/OwnedMediaPlatformRollupWeeklyInner.md)
- [OwnedMediaProfile](docs/OwnedMediaProfile.md)
- [OwnedMediaProfileSettings](docs/OwnedMediaProfileSettings.md)
- [OwnedMediaProfilesResponse](docs/OwnedMediaProfilesResponse.md)
- [OwnedMediaProfilesUpdateResponse](docs/OwnedMediaProfilesUpdateResponse.md)
- [OwnedMediaRow](docs/OwnedMediaRow.md)
- [OwnedMediaStoreTotals](docs/OwnedMediaStoreTotals.md)
- [OwnedMediaSummaryResponse](docs/OwnedMediaSummaryResponse.md)
- [OwnedMediaSummaryResponsePrevious](docs/OwnedMediaSummaryResponsePrevious.md)
- [OwnedMediaWeek](docs/OwnedMediaWeek.md)
- [PaginatedEnvelope](docs/PaginatedEnvelope.md)
- [Ping200Response](docs/Ping200Response.md)
- [Project](docs/Project.md)
- [ProjectCreateRequest](docs/ProjectCreateRequest.md)
- [ProjectCreateRequestCollectionsInner](docs/ProjectCreateRequestCollectionsInner.md)
- [ProjectCreateRequestCompetitorsInner](docs/ProjectCreateRequestCompetitorsInner.md)
- [ProjectCreateRequestOwnedMedia](docs/ProjectCreateRequestOwnedMedia.md)
- [ProjectCreateResponse](docs/ProjectCreateResponse.md)
- [ProjectCreateResponseCollectionsInner](docs/ProjectCreateResponseCollectionsInner.md)
- [ProjectCreateResponseCompetitors](docs/ProjectCreateResponseCompetitors.md)
- [ProjectCreateResponseEmailSubscription](docs/ProjectCreateResponseEmailSubscription.md)
- [ProjectCreateResponseLimits](docs/ProjectCreateResponseLimits.md)
- [ProjectCreateResponsePrompts](docs/ProjectCreateResponsePrompts.md)
- [ProjectCreateResponseSameDomainProjectsInner](docs/ProjectCreateResponseSameDomainProjectsInner.md)
- [ProjectDetails](docs/ProjectDetails.md)
- [ProjectDetailsAllOfAgentTraffic](docs/ProjectDetailsAllOfAgentTraffic.md)
- [ProjectDetailsAllOfAiTraffic](docs/ProjectDetailsAllOfAiTraffic.md)
- [ProjectDetailsAllOfDataCoverage](docs/ProjectDetailsAllOfDataCoverage.md)
- [ProjectDetailsAllOfSearchConsole](docs/ProjectDetailsAllOfSearchConsole.md)
- [ProjectDetailsAllOfStats](docs/ProjectDetailsAllOfStats.md)
- [ProjectDetailsAllOfStatsPromptsByBrandKind](docs/ProjectDetailsAllOfStatsPromptsByBrandKind.md)
- [ProjectProfile](docs/ProjectProfile.md)
- [ProjectUpdateResponse](docs/ProjectUpdateResponse.md)
- [PromptCategorization](docs/PromptCategorization.md)
- [PromptCategorizationResponse](docs/PromptCategorizationResponse.md)
- [PromptExecutionRecord](docs/PromptExecutionRecord.md)
- [PromptExecutionsResponse](docs/PromptExecutionsResponse.md)
- [PromptGenerationRequest](docs/PromptGenerationRequest.md)
- [PromptGenerationResponse](docs/PromptGenerationResponse.md)
- [PromptGenerationResponseError](docs/PromptGenerationResponseError.md)
- [PromptGenerationResponseParams](docs/PromptGenerationResponseParams.md)
- [PromptRecord](docs/PromptRecord.md)
- [PromptSummaryResponse](docs/PromptSummaryResponse.md)
- [PromptSummaryRow](docs/PromptSummaryRow.md)
- [PromptTagsAssignResponse](docs/PromptTagsAssignResponse.md)
- [PromptTagsRemoveResponse](docs/PromptTagsRemoveResponse.md)
- [PromptsCreateRequest](docs/PromptsCreateRequest.md)
- [PromptsCreateResponse](docs/PromptsCreateResponse.md)
- [PromptsCreateResponseDataInner](docs/PromptsCreateResponseDataInner.md)
- [PromptsImportRequest](docs/PromptsImportRequest.md)
- [PromptsImportRequestRowsInner](docs/PromptsImportRequestRowsInner.md)
- [PromptsImportResponse](docs/PromptsImportResponse.md)
- [PromptsImportResponseRowErrorsInner](docs/PromptsImportResponseRowErrorsInner.md)
- [PromptsResponse](docs/PromptsResponse.md)
- [QueryWebAnalyticsRequest](docs/QueryWebAnalyticsRequest.md)
- [RecommendationItem](docs/RecommendationItem.md)
- [RecommendationItemUpdateResponse](docs/RecommendationItemUpdateResponse.md)
- [RecommendationSummary](docs/RecommendationSummary.md)
- [RecommendationSummarySummary](docs/RecommendationSummarySummary.md)
- [RecommendationsResponse](docs/RecommendationsResponse.md)
- [RemovePromptTagsRequest](docs/RemovePromptTagsRequest.md)
- [RemoveTeamMember200Response](docs/RemoveTeamMember200Response.md)
- [RevokeTeamInvitation200Response](docs/RevokeTeamInvitation200Response.md)
- [SampleWebhookPayloads200Response](docs/SampleWebhookPayloads200Response.md)
- [SampleWebhookPayloads200ResponseDataInner](docs/SampleWebhookPayloads200ResponseDataInner.md)
- [SearchConsoleExcludedProperty](docs/SearchConsoleExcludedProperty.md)
- [SearchConsoleFiltersInner](docs/SearchConsoleFiltersInner.md)
- [SearchConsoleListResponse](docs/SearchConsoleListResponse.md)
- [SearchConsoleListResponseDataInner](docs/SearchConsoleListResponseDataInner.md)
- [SearchConsoleMetrics](docs/SearchConsoleMetrics.md)
- [SearchConsolePropertiesResponse](docs/SearchConsolePropertiesResponse.md)
- [SearchConsolePropertiesResponseDataInner](docs/SearchConsolePropertiesResponseDataInner.md)
- [SearchConsoleProperty](docs/SearchConsoleProperty.md)
- [SearchConsolePropertyError](docs/SearchConsolePropertyError.md)
- [SearchConsoleRowsResponse](docs/SearchConsoleRowsResponse.md)
- [SearchConsoleRowsResponseDataInner](docs/SearchConsoleRowsResponseDataInner.md)
- [SearchConsoleSummaryResponse](docs/SearchConsoleSummaryResponse.md)
- [SearchConsoleSummaryResponseBreakdownInner](docs/SearchConsoleSummaryResponseBreakdownInner.md)
- [SearchConsoleTimeseriesResponse](docs/SearchConsoleTimeseriesResponse.md)
- [SearchConsoleTimeseriesResponseDataInner](docs/SearchConsoleTimeseriesResponseDataInner.md)
- [SendCustomReportRequest](docs/SendCustomReportRequest.md)
- [SentimentBreakdownBrand](docs/SentimentBreakdownBrand.md)
- [SentimentBreakdownCounts](docs/SentimentBreakdownCounts.md)
- [SentimentBreakdownEnvelope](docs/SentimentBreakdownEnvelope.md)
- [SentimentRecord](docs/SentimentRecord.md)
- [SentimentTagRow](docs/SentimentTagRow.md)
- [SentimentTagsResponse](docs/SentimentTagsResponse.md)
- [SentimentTopicRow](docs/SentimentTopicRow.md)
- [SentimentTopicsResponse](docs/SentimentTopicsResponse.md)
- [SentimentsResponse](docs/SentimentsResponse.md)
- [SovResponse](docs/SovResponse.md)
- [SovResponseBreakdownInner](docs/SovResponseBreakdownInner.md)
- [SovResponseCurrentInner](docs/SovResponseCurrentInner.md)
- [SovResponseOthersInner](docs/SovResponseOthersInner.md)
- [SovResponseOverTimeInner](docs/SovResponseOverTimeInner.md)
- [SovResponsePeriodsInner](docs/SovResponsePeriodsInner.md)
- [SovResponseSample](docs/SovResponseSample.md)
- [StoreConnectionResponse](docs/StoreConnectionResponse.md)
- [StoreConnectionResponseAccount](docs/StoreConnectionResponseAccount.md)
- [StoreConnectionResponseCandidatesInner](docs/StoreConnectionResponseCandidatesInner.md)
- [StoreConnectionResponseProject](docs/StoreConnectionResponseProject.md)
- [SuggestedPrompt](docs/SuggestedPrompt.md)
- [SuggestedPromptIdsRequest](docs/SuggestedPromptIdsRequest.md)
- [SuggestedPromptsAcceptRequest](docs/SuggestedPromptsAcceptRequest.md)
- [SuggestedPromptsAcceptResponse](docs/SuggestedPromptsAcceptResponse.md)
- [SuggestedPromptsAcceptResponseAcceptedInner](docs/SuggestedPromptsAcceptResponseAcceptedInner.md)
- [SuggestedPromptsRejectResponse](docs/SuggestedPromptsRejectResponse.md)
- [SuggestedPromptsResponse](docs/SuggestedPromptsResponse.md)
- [SummaryResponse](docs/SummaryResponse.md)
- [SummaryResponseAllOfPositionDistribution](docs/SummaryResponseAllOfPositionDistribution.md)
- [SummaryResponseAllOfSummaryValueInner](docs/SummaryResponseAllOfSummaryValueInner.md)
- [TagRef](docs/TagRef.md)
- [TeamAccountRole](docs/TeamAccountRole.md)
- [TeamInvitation](docs/TeamInvitation.md)
- [TeamMember](docs/TeamMember.md)
- [TechnicalGeoReportContentRevertRequest](docs/TechnicalGeoReportContentRevertRequest.md)
- [TechnicalGeoReportContentUpdateRequest](docs/TechnicalGeoReportContentUpdateRequest.md)
- [TechnicalGeoReportContentUpdateRequestEdits](docs/TechnicalGeoReportContentUpdateRequestEdits.md)
- [TechnicalGeoReportContentUpdateResponse](docs/TechnicalGeoReportContentUpdateResponse.md)
- [TimeseriesPoint](docs/TimeseriesPoint.md)
- [TimeseriesResponse](docs/TimeseriesResponse.md)
- [TimeseriesSeries](docs/TimeseriesSeries.md)
- [TopSourcesResponse](docs/TopSourcesResponse.md)
- [TopSourcesResponseDataInner](docs/TopSourcesResponseDataInner.md)
- [UpdateAnnotationRequest](docs/UpdateAnnotationRequest.md)
- [UpdateCollectionRequest](docs/UpdateCollectionRequest.md)
- [UpdateCompetitorRequest](docs/UpdateCompetitorRequest.md)
- [UpdateOwnedMediaProfilesRequest](docs/UpdateOwnedMediaProfilesRequest.md)
- [UpdateProjectDraftRequest](docs/UpdateProjectDraftRequest.md)
- [UpdateProjectRequest](docs/UpdateProjectRequest.md)
- [UpdatePromptRequest](docs/UpdatePromptRequest.md)
- [UpdateRecommendationItemRequest](docs/UpdateRecommendationItemRequest.md)
- [WebAnalyticsQueryResponse](docs/WebAnalyticsQueryResponse.md)
- [WebAnalyticsQueryResponseColumnsInner](docs/WebAnalyticsQueryResponseColumnsInner.md)
- [WebAnalyticsSchemaResponse](docs/WebAnalyticsSchemaResponse.md)

### Authorization


Authentication schemes defined for the API:
<a id="BearerAuth"></a>
#### BearerAuth


- **Type**: HTTP Bearer Token authentication

## About

This TypeScript SDK client supports the [Fetch API](https://fetch.spec.whatwg.org/)
and is automatically generated by the
[OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.71.0`
- Package version: `1.71.0`
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
