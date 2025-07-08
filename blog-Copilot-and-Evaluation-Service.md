# Closing the Loop: Evaluating Copilot Studio Agents with Azure AI Observability

In today’s fast-evolving world of generative AI, agent creation has never been easier—or more popular. With tools like Copilot Studio, business users and developers alike are spinning up AI-powered agents to automate tasks, answer customer questions, and drive productivity. But with great power comes great responsibility—and increasingly, our customers are asking an important question:

> **“How do we know these agents are performing well and safely?”**

This is where **observability** and **evaluation** enter the picture.

## Why Observability Matters for AI Agents

As outlined in [Azure AI Foundry](https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/observability), observability isn’t just for DevOps pipelines—it’s essential for AI systems. It’s the process of collecting, analyzing, and acting on signals from your AI applications to ensure they’re reliable, safe, and aligned with business goals.

Without observability, hallucinations or off-topic responses may go unnoticed until they cause customer frustration—or worse.

In fact, Microsoft recommends that AI solutions follow **continuous monitoring and evaluation** practices. This includes capturing runtime metrics, logging interactions, and continuously evaluating those interactions against key criteria. You can learn more about this approach [here](https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/monitor-applications) and [here](https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/continuous-evaluation-agents).

## Introducing My Solution: Copilot Studio + Azure AI Observability

To address this need, I built a solution that connects Copilot Studio agents with Azure AI Observability and Evaluation services. Here’s how it works:

1. **Conversation Capture**  
Every conversation with your Copilot Studio agent is automatically stored in Dataverse tables (standard functionality).

2. **Evaluation Pipeline**  
My solution extracts these conversations and sends them to **Azure AI Observability** via the **Evaluation API**.

3. **Evaluation & Insights**  
The Azure AI Evaluation Service analyzes the conversations using various **evaluators**, including:
- **General Purpose Evaluators**: For relevance, fluency, and coherence ([details](https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/evaluation-evaluators/general-purpose-evaluators))
- **Risk & Safety Evaluators**: For harmful content, bias, and security issues ([details](https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/evaluation-evaluators/risk-safety-evaluators))

4. **Dataverse Reporting (Out-of-the-Box)**  
Once the evaluations are complete, the results are automatically stored back into Dataverse. To make it even easier to analyze the data, this solution includes **pre-built Power BI reports** that work right out of the box.

These reports allow you to:
- Track key metrics like Relevance, Fluency, Coherence, and Safety
- Filter results by time period, agent, or evaluator type
- Drill into individual conversations for detailed review

No need to start from scratch—simply import the provided Power BI reports following [these steps](https://github.com/v7herman4/copilotstudio-and-azure-evaluation-service/blob/main/documentation/howtousereporting.md), and you’ll have instant visibility into your agents’ performance and risk areas.

In other words:  
➡️ **Extract Copilot Studio conversations → Evaluate in Azure → Visualize in Dataverse (with reporting ready to go).**

## Why This Matters

This approach unlocks **continuous improvement** for your Copilot Studio agents:
- Detect hallucinations and harmful responses early
- Identify areas where your agents need refinement
- Monitor long-term performance trends
- Keep humans in the loop for critical evaluations

It also aligns perfectly with Microsoft’s [AI principles](https://www.microsoft.com/ai/responsible-ai) around safety, transparency, and accountability.

## Get Started

The full solution is open-source and available [here on GitHub](https://github.com/v7herman4/copilotstudio-and-azure-evaluation-service). You’ll find:
- Power Platform solution files
- Azure Function for evaluation integration
- Setup instructions for connecting to your environment

Whether you’re a seasoned AI developer or just beginning your Copilot Studio journey, this project will help you create **better, safer, and more accountable agents**.
