# ADR 005: AI Provider

**Date:** 2025-10-8 \
**Status:** Accepted

## Context  
We need to implement intelligent scheduling logic in our Chrome extension. The system must generate optimized study schedules that consider user habits, goals, and constraints. To achieve this, we require a reliable LLM for reasoning (Gemini) combined with Operations Research (OR) techniques for optimization. Additionally, we want to support exporting schedules to standard calendar formats (.ics) for seamless integration with tools like Google Calendar, Outlook, and Apple Calendar.

## Decision  
We will use Google Gemini API (via AI Studio) instead of Vertex AI for now.
- Vertex AI offers scalability and integration but requires OAuth setup and additional cloud configuration.
- For faster prototyping and development, the standalone Gemini API provides a simpler developer experience with direct API key authentication.
- At this stage, Operations Research (OR) integration will be deprioritized. The initial product will focus on extracting tasks/events and generating simple schedules using Gemini.
- If more advanced optimization (via OR) becomes necessary, we can later migrate from AI Studio → Vertex AI using Google’s supported migration path.

## Consequences  
- **Positive:**  
  - Simple setup with API keys (no OAuth required).
  - Faster iteration during early development.
  - Retains Gemini’s reasoning and language understanding.
  - .ics export continues to provide calendar interoperability.
  - Clear migration path if OR or scaling becomes necessary.  

- **Negative:**  
  -	No built-in OR integration at this stage.
  -	Less scalable than Vertex AI-managed infrastructure.
  -	Future work may be required to re-integrate OR when scaling.
   
## Migration Path

If OR or large-scale production needs arise, we can migrate from AI Studio Gemini API to Vertex AI with minimal changes, as outlined in Google’s official documentation:
[Migration Guide: AI Studio → Vertex AI](https://cloud.google.com/vertex-ai/generative-ai/docs/migrate/migrate-google-ai)


## Alternatives Considered 
- **Option A: Vertex AI (Gemini + OR integration)**
  - Pros: Production-ready, tight GCP integration.
  - Cons: Requires OAuth setup, more complex dev process.
    
- **Option B: OpenAI (GPT-4.0/5.0):**  
  - Pros: Strong general reasoning and text generation.  
  - Cons: Lacks built-in OR tooling; would require external optimization frameworks and integrations.  

- **Option C: Claude (Anthropic):**  
  - Pros: Excellent for reasoning and alignment.  
  - Cons: No native integration with OR or Vertex ecosystem; would require additional services for optimization and deployment.  

## References  
- [Google AI Studio Documentation](https://ai.google.dev/gemini-api/docs)
- [Google Vertex AI Documentation](https://cloud.google.com/vertex-ai/docs)  
- [Google OR-Tools](https://developers.google.com/optimization)  
- [iCalendar (.ics) Specification](https://icalendar.org/RFC-Specifications/iCalendar-RFC-5545/)

