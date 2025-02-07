# Week5: Production Design
In the final week, we focus on deploying the partner's AI application to the production environment. To ensure that the AI application operates as intended in the production environment, it is essential to guarantee its quality and address security concerns. Over the course of Weeks 1 to 4, we have discussed the definition of success and measurement methods, and we will improve the AI application based on these discussions. Week 5 provides monitoring methods to implement these measurements from a system perspective. Security is the most fundamental and important element. Microsoft can provide security approaches and frameworks proposed for production. Based on the available information, we will collaborate with Microsoft to discuss and further enhance the AI application for production release, supporting the partner's business growth.

# Goal
Ensure quality and security to publish to production environment

# Contents is here;
*This sentence is under construction.*

**For Internal**
- Optimize and monitoring performance
- Enhance security in their AI App

This link may help us?
- Sample Reference
    - https://learn.microsoft.com/en-us/azure/architecture/ai-ml/architecture/basic-openai-e2e-chat

![alt text](image.png)

## Workflow of architecture
1. A user issues an HTTPS request to the app service default domain on azurewebsites.net. This domain automatically points to the App Service built-in public IP. The Transport Layer Security (TLS) connection is established from the client directly to App Service. The certificate is managed completely by Azure.
2. Easy Auth, a feature of Azure App Service, ensures that the user accessing the site is authenticated with Microsoft Entra ID.
3. The client application code deployed to App Service handles the request and presents the user a chat UI. The chat UI code connects to APIs also hosted in that same App Service instance. The API code connects to an Azure Machine Learning managed online endpoint to handle user interactions.
4. The managed online endpoint routes the request to Azure Machine Learning managed compute where the prompt flow orchestration logic is deployed.
5. The prompt flow orchestration code begins executing. Among other things, the logic extracts the user's query from the request.
6. The orchestration logic connects to Azure AI Search to fetch grounding data for the query. The grounding data is added to the prompt that is sent to Azure OpenAI in the next step.
7. The orchestration logic connects to Azure OpenAI and sends the prompt that includes the relevant grounding data.
8. The information about original request to App Service and the call to the managed online endpoint are logged in Application Insights, using the same Log Analytics workspace that Azure OpenAI telemetry flows to.

##AI Operations##

##AI Copilots and Chat Applications##
1. Multitenancy - segregation of data, APIs - 
2. Pipelines
3. Resilience
4. Load balancing (which is different to web load balancing... - time to response for a chat answer etc). AOAI deployment types...
5. Monitoring
6. Tracing
7. Security
8. Prompt library management
9. Prompt Chaining
10. Responsible AI - Failure modes

##AI Agents##
