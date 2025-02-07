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

# AIOps/GenAIOps/LLMOps
Just as DevOps activities and processes cover the entire application development lifecycle management through automated continuous integration and continuous deployment (CI/CD) pipelines and monitoring - GenAIOps focuses on processes, data curation and consumption, ensuring efficiency and adherence to standards like quality, reliability, security, and ethics and includes the data pipeline as one of the core components.

AI applications are inherently nondeterministic and many AI models are prone to producing different answers for the same inquiry during inference. Therefore AI apps need processes that can manage and adapt to the unpredictability of AI outputs. 

DataOps extends into MLOps, which operationalizes machine learning workflows for model training and testing. GenAIOps, a specialized subset of MLOps, targets generative AI solutions. It involves tasks like model discovery and refining pretrained models with enriched data.

1. DevOps: Manages the application development lifecycle with automated CI/CD pipelines.

2. DataOps: Specializes in managing the data lifecycle, including ETL/ELT processes.

3. MLOps: Operationalizes machine learning workflows for model training and testing.

4. GenAIOps: Focuses on generative AI solutions, involving tasks like model discovery and refinement.

AI workloads are unpredictable and require processes to manage this unpredictability. The methodologies overlap, and their relevance depends on the type of AI, such as discriminative or generative AI. The goal is to deliver capability with efficient operations throughout the development lifecycle.

Expected outcomes include:

- Repeatable processes with consistent results.
- Sustained accuracy of models.
- Effective governance.
- Change management for adapting to model drift.
- Automation and monitoring.

Proper tracking mechanisms and standardized processes are crucial to avoid risks like repeated errors, low-quality data, and loss of user confidence. Implementing established processes with specialized tools is essential for managing AI/ML workflows.

![image](https://github.com/user-attachments/assets/80a7a09a-1c68-4896-be33-b1dc3ae7eeb6)

Well Architected Framework for  MLOps and GenAIOps for AI Workloads on Azure: https://learn.microsoft.com/en-us/azure/well-architected/ai/mlops-genaiops

MLOps Solution Accelerator: https://github.com/Azure/mlops-v2



# AI Copilots and Chat Applications
## 1. Multitenancy - segregation of data, APIs - 
## 2. Pipelines
## 3. Resilience
## 4. Load balancing (which is different to web load balancing... - time to response for a chat answer etc). AOAI deployment types...
## 5. Monitoring
## 6. Tracing
## 7. Security
## 8. Prompt library management
## 9. Prompt Chaining
## 10. Responsible AI - Failure modes

# AI Agents

