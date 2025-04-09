# Bootcamp Feedback Collector

The **Bootcamp Feedback Collector** is an automated agent designed to reach out to bootcamp students after their program and gather structured feedback via phone or chat. It uses a simple intent classifier to determine if the student's response falls into one of four categories: positive feedback, negative (bad) feedback, inquiries, or none (no match). The agent then follows up accordingly with stage-specific prompts.

## Features

- **Conversational Agent:**  
  Engages in a friendly, natural conversation to gather post-bootcamp feedback.
  
- **Intent Classification:**  
  Determines whether a student's response is:
  - `positive_feedback`
  - `bad_feedback`
  - `inquiries`
  - `none` (fallback for off-topic or unclear responses)
  
- **Stage-based Follow-up:**  
  Depending on the classified intent, the agent offers specific follow-up questions to collect detailed insights.

- **Knowledge Integration for Inquiries:**  
  The agent can reference a provided knowledge base with bootcamp details (such as dates, location, curriculum highlights) to answer any questions students have.

## Architecture Overview

The system is divided into two primary components:

1. **Intent Classifier & Stage Controller:**  
   - **Intent Classifier Prompt:**  
     A prompt that processes user responses to classify the intent into one of the categories.  
   - **Stage Handling:**  
     Based on the classification, the agent sends a follow-up message:
      - For `positive_feedback`: It asks for more details on what was enjoyed.
      - For `bad_feedback`: It politely asks for more details on what could be improved.
      - For `inquiries`: It answers student questions using a provided knowledge base.
      - For `none`: It politely redirects the conversation back on track.
      
2. **Knowledge Base Integration:**  
   - A text file or inline information source that contains bootcamp details (e.g., event name, dates, benefits, registration links, etc.) is used by the agent when answering inquiries.
