# Week5: Production Design
In the final week, we focus on deploying the partner's AI application to the production environment. To ensure that the AI application operates as intended in the production environment, it is essential to guarantee its quality and address security concerns. Over the course of Weeks 1 to 4, we have discussed the definition of success and measurement methods, and we will improve the AI application based on these discussions. Week 5 provides monitoring methods to implement these measurements from a system perspective. Security is the most fundamental and important element. Microsoft can provide security approaches and frameworks proposed for production. Based on the available information, we will collaborate with Microsoft to discuss and further enhance the AI application for production release, supporting the partner's business growth.

# Goal
Ensure quality and security to publish to production environment

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
## 5. Monitoring, Tracing & Automation
Monitoring, tracking, and automation are crucial strategies for operations. The goal throughout the development lifecycle is to deliver functionality through efficient operations. Key elements to achieve this are monitoring, tracking, and automation. An operational strategy involves daily monitoring, tracking, and automation of processes implemented by AI. These tasks must be performed using appropriate tools, and without these processes, the following risks may arise:

- Repeated errors and non-reproducibility in data processing, model hosting, ground data management, and other tasks.
- Low-quality or outdated data used for model training and refinement.
- Impact on end-user confidence in the system, potentially leading to legal, compliance, or security issues in the worst-case scenario.

To mitigate these risks, it is essential to use a complete set of tools and implement established processes. Specialized tools can be used to manage AI/machine learning workflows in various environments.

### Monitoring, Tracing
Monitoring is a crucial strategy that should be applied at all stages. It is a continuous process that functions as an input to quality gates, ensuring consistency and reliability throughout the development lifecycle and rigorous testing of AI workloads. Models need to be monitored from both operational and data science perspectives.

Implement an internal loop monitoring process within DataOps to measure proximity to the acceptance quality bar and check for anomalies.

For pre-trained models, it is also important to monitor data errors and performance with a focus on relevance. Evaluate inputs (prompts) and outputs (input candidates) to ensure they are highly relevant and accurate. Additionally, be aware of security risks, such as attempts to manipulate model behavior using malicious prompts. Ensure there is comprehensive content moderation to inspect bidirectional data and exclude inappropriate content. These considerations are explained in the [ResponsibleAI design area](https://learn.microsoft.com/en-us/azure/well-architected/ai/responsible-ai).

![image](https://learn.microsoft.com/en-us/azure/well-architected/ai/images/responsible-ai.png#lightbox)

Post-deployment, monitoring operations are necessary to address issues like model degradation. Changes in data or external factors can cause models to become outdated and produce irrelevant results. As a proactive measure, use automated processes for continuous monitoring, evaluation, and retraining to maintain accuracy and relevance. Furthermore, like other workloads, it is essential to monitor infrastructure and workload metrics to ensure optimal performance and reliability. For more details, refer to ["Testing for Model Decay"](https://learn.microsoft.com/en-us/azure/well-architected/ai/test#prevent-model-decay).

- Tools
Invest in tools that make it easier to collect metrics from inference endpoints, like Azure Machine Learning Data collector.
You also need observability of model performance, data drift, and safety and quality for generative AI.
For more information, see these articles:

  - [Data collection from models in production](https://learn.microsoft.com/en-us/azure/machine-learning/concept-data-collection)
  - [Model monitoring with Azure Machine Learning](https://learn.microsoft.com/en-us/azure/machine-learning/concept-model-monitoring?view=azureml-api-2)
  - [Content filtering in Azure AI Foundry portal](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/content-filtering)

### Automation, Deployment Pipelines, and Model Maintenance
Automation is a crucial strategy for ensuring repeatability and efficiency throughout the AI workload lifecycle. It helps reduce errors and inconsistencies caused by manual processes, leading to consistent results and saving time and resources by automating repetitive tasks. Automation is essential for managing the complexity of AI workloads, which involve frequent changes and interrelated steps.

Deployment pipelines are another key component. They provide repeatable infrastructure deployment and continuous integration of code, which helps in building, testing, and validating models before promoting them to production environments. Implementing deployment pipelines enhances reliability and improves the overall user experience of workloads.

Model maintenance is also critical. Post-deployment, monitoring operations are necessary to address issues like model degradation and drift. Changes in data or external factors can cause models to become outdated and produce irrelevant results. To mitigate these risks, structured processes for continuous monitoring, evaluation, and retraining are essential. This ensures that models maintain their accuracy and relevance over time.

In summary, automation, deployment pipelines, and model maintenance are essential elements in the operation of AI workloads. By using the right tools and processes, you can manage these workloads efficiently and securely, ensuring optimal performance and reliability.

- Tools
For more details, you can refer to the Azure Well-Architected Framework documentation on MLOps and GenAIOps for AI Workloads;
  - [Use Azure Pipelines with Azure Machine Learning](https://learn.microsoft.com/en-us/azure/machine-learning/how-to-devops-machine-learning) 
  - [Which Azure pipeline technology should I use?](https://learn.microsoft.com/en-us/azure/machine-learning/concept-ml-pipelines#which-azure-pipeline-technology-should-i-use)

### GenAIOps
To achieve an efficient workload operational lifecycle, it is essential to incorporate GenAIOps. GenAIOps is a methodology derived from MLOps, designed to streamline the operation and management of generative AI solutions. It explains operational practices and strategies for managing large language models (LLMs) in production environments. Let's promote GenAIOps based on the current maturity level of your organization.

![GenAIOps Maturity Levels](https://learn.microsoft.com/en-us/azure/machine-learning/media/concept-llmops-maturity/llmopsml.png?view=azureml-api-2#lightbox)

You can evaluate your organization's current maturity level on [GenAIOps Maturity Model Assessment](https://learn.microsoft.com/en-us/assessments/e14e1e9f-d339-4d7e-b2bb-24f056cf08b6/). Let's start here!

![image](https://github.com/user-attachments/assets/e44f4256-ce40-4f78-a725-32701bd239fc)


- **Level 1 - initial: Score from [GenAIOps Maturity Model Assessment](https://learn.microsoft.com/en-us/assessments/e14e1e9f-d339-4d7e-b2bb-24f056cf08b6/) is initial (0-9).** \
  Your organization is at the initial foundational stage of GenAIOps maturity. You're exploring the capabilities of LLMs but haven't yet developed structured practices or systematic approaches. Begin by familiarizing yourself with different LLM APIs and their capabilities. Next, start experimenting with structured prompt design and basic prompt engineering. Review Microsoft Learning articles as a starting point. Taking what you’ve learned, discover how to introduce basic metrics for LLM application performance evaluation.

  **Suggested references for level 1 advancement**
  - [Azure AI Foundry Model Catalog](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/model-catalog)
  - [Explore the Azure AI Foundry portal Model Catalog](https://www.youtube.com/watch?v=GS5ZIiNqcEY)
  - [Introduction to Prompt Engineering](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering)
  - [Prompt Engineering Techniques](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/advanced-prompt-engineering?pivots=programming-language-chat-completions)
  - [System Message Framework](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/system-message)
  - [Prompt Flow in Azure AI Foundry portal](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow)
  - [Evaluate GenAI Applications with Azure AI Foundry](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/evaluation-approach-gen-ai)
  - [GenAI Evaluation and Monitoring Metrics with Azure AI Foundry](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/evaluation-metrics-built-in)

  To better understand GenAIOps, consider available MS Learning courses and workshops.
  - [Microsoft Azure AI Fundaments: GenAI](https://learn.microsoft.com/en-us/training/paths/introduction-generative-ai/)
  - [GenAI for Beginners Course](https://techcommunity.microsoft.com/t5/educator-developer-blog/generative-ai-for-beginners-a-12-lesson-course/ba-p/3968583)
  
- **Level 2 - deifined: Score from [GenAIOps Maturity Model Assessment](https://learn.microsoft.com/en-us/assessments/e14e1e9f-d339-4d7e-b2bb-24f056cf08b6/) is maturing(10-14).** \
  Your organization has started to systematize LLM operations, with a focus on structured development and experimentation. However, there's room for more sophisticated integration and optimization. To improve your capabilities and skills, learn how to develop more complex prompts and begin integrating them effectively into applications. During this journey, you’ll want to implement a systematic approach for LLM application deployment, possibly exploring CI/CD integration. Once you understand the core, you can begin employing more advanced evaluation metrics like groundedness, relevance, and similarity. Ultimately, you’ll want to focus on content safety and ethical considerations in LLM usage.

  **Suggested references for level 2 advancement**
  - Take our [step-by-step workshop to elevate your GenAIOps practices](https://github.com/microsoft/llmops-workshop?tab=readme-ov-file)
  - [Prompt Flow in Azure AI Foundry portal](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow)
  - [How to Build with Prompt Flow](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/flow-develop)
  - [Deploy a Flow as a Managed Online endpoint for Real-Time Inference](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/flow-deploy?tabs=azure-studio)
  - [Integrate Prompt Flow with GenAIOps](https://learn.microsoft.com/en-us/azure/machine-learning/prompt-flow/how-to-integrate-with-llm-app-devops?tabs=cli)
  - [GenAI Evaluation with Azure AI Foundry](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/evaluation-approach-gen-ai)
  - [GenAI Evaluation and Monitoring Metrics](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/evaluation-metrics-built-in)
  - [Azure Content Safety](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview)
  - [Responsible AI Tools and Practices](https://azure.microsoft.com/blog/infuse-responsible-ai-tools-and-practices-in-your-llmops)

- **Level 3 - managed: Score from [GenAIOps Maturity Model Assessment](https://learn.microsoft.com/en-us/assessments/e14e1e9f-d339-4d7e-b2bb-24f056cf08b6/) is maturing (15-19).** \
  Your organization is managing advanced LLM workflows with proactive monitoring and structured deployment strategies. You're close to achieving operational excellence. To expand your base knowledge, focus on continuous improvement and innovation in your LLM applications. As you progress, you can enhance your monitoring strategies with predictive analytics and comprehensive content safety measures. Learn to optimize and fine-tune your LLM applications for specific requirements. Ultimately, you want to strengthen your asset management strategies through advanced version control and rollback capabilities.

  **Suggested references for level 3 advancement**
  - [Fine-tuning with Azure ML Learning](https://learn.microsoft.com/en-us/training/modules/finetune-foundation-model-with-azure-machine-learning/)
  - [Model Customization with Fine-tuning](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/fine-tuning?tabs=turbo%2Cpython&pivots=programming-language-studio)
  - [GenAI Model Monitoring](https://learn.microsoft.com/en-us/azure/machine-learning/prompt-flow/how-to-monitor-generative-ai-applications)
  - [Elevate LLM Apps to Production with GenAIOps](https://techcommunity.microsoft.com/t5/ai-machine-learning-blog/elevate-your-llm-applications-to-production-via-llmops/ba-p/3979114)

- **Level 4 - optimized: Score from [GenAIOps Maturity Model Assessment](https://learn.microsoft.com/en-us/assessments/e14e1e9f-d339-4d7e-b2bb-24f056cf08b6/) is optimized (20-28).** \
   Your organization demonstrates operational excellence in GenAIOps. You have a sophisticated approach to LLM application development, deployment, and monitoring. As LLMs evolve, you’ll want to maintain your cutting-edge position by staying updated with the latest LLM advancements. Continuously evaluate the alignment of your LLM strategies with evolving business objectives. Ensure that you foster a culture of innovation and continuous learning within your team. Last, but not least, share your knowledge and best practices with the wider community to establish thought leadership in the field.

  **Suggested references for advanced techniques**
  - [Azure AI Foundry Model Catalog](https://ai.azure.com/explore/models)
  - [Evaluation of GenAI applications](https://learn.microsoft.com/en-us/azure/ai-studio/concepts/evaluation-approach-gen-ai)

## 6. Security
## 7. Prompt library management
## 8. Prompt Chaining
## 9. Responsible AI - Failure modes

# AI Agents

