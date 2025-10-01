# ADR 005: Vertex AI

**Date:** 2025-09-30  
**Status:** Proposed  

## Context  
We need to implement intelligent scheduling logic in our Chrome extension. The system must generate optimized study schedules that consider user habits, goals, and constraints. To achieve this, we require a reliable LLM for reasoning (Gemini) combined with **Operations Research (OR)** techniques for optimization. Additionally, we want to support exporting schedules to standard calendar formats (`.ics`) for seamless integration with tools like Google Calendar, Outlook, and Apple Calendar.  

## Decision  
We will use **Vertex AI** with **Gemini + OR integration**. Vertex AI provides a scalable environment for combining LLM reasoning with optimization models. Gemini will handle natural language understanding and reasoning for personalized schedules, while OR techniques (e.g., linear programming, constraint solving) will ensure schedules meet user-defined constraints.  
The final schedules will be exported as `.ics` files, enabling users to import their schedules into any calendar application.  

## Consequences  
- **Positive:**  
  - Tight integration of reasoning (Gemini) with optimization (OR).  
  - Scalable and production-ready infrastructure via Vertex AI.  
  - Flexibility to extend with additional AI/ML services in the future.  
  - `.ics` export provides interoperability with standard calendar apps.  

- **Negative:**  
  - Vendor lock-in with Google Cloud (pricing and ecosystem).  
  - Requires setup and configuration of Vertex AI services.  
  - More complex architecture compared to a single LLM provider.  

## Alternatives Considered  
- **Option A: OpenAI (GPT-4.0/5.0):**  
  - Pros: Strong general reasoning and text generation.  
  - Cons: Lacks built-in OR tooling; would require external optimization frameworks and integrations.  

- **Option B: Google AI Studio (standalone Gemini):**  
  - Pros: Simple, lightweight for prototyping Gemini models.  
  - Cons: Limited orchestration and integration; less flexible for combining with OR.  

- **Option C: Claude (Anthropic):**  
  - Pros: Excellent for reasoning and alignment.  
  - Cons: No native integration with OR or Vertex ecosystem; would require additional services for optimization and deployment.  

## References  
- [Google Vertex AI Documentation](https://cloud.google.com/vertex-ai/docs)  
- [Google OR-Tools](https://developers.google.com/optimization)  
- [iCalendar (.ics) Specification](https://icalendar.org/RFC-Specifications/iCalendar-RFC-5545/)  
