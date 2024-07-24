# Agentic Writer Workflow Prototype Specification

## 1. Overview
This prototype will implement a simplified version of the Agentic Writer Workflow to test the core functionality of AI-assisted content creation from YouTube video transcriptions.

## 2. Key Features for Prototype
- YouTube video transcription processing
- AI-driven content drafting
- Basic review and scoring system
- Simple user interface for content viewing and minimal editing

## 3. Simplified System Architecture

### 3.1 Backend (Python + FastAPI + Crew AI)
**Components:**
- **FastAPI Server:** Handles basic API requests; no authentication for prototype.
- **Crew AI Integration:** Implements core AI agents.
- **YouTube API Service:** Basic video information retrieval and transcription downloads.
- **Simple Database (SQLite):** Local storage for prototype data.

**Agents:**
- **Transcription Agent:** Processes YouTube video links and retrieves transcriptions.
- **Drafting Agent:** Generates initial drafts from transcriptions.
- **Review Agent:** Evaluates drafts and provides a simple score.

### 3.2 Frontend (Simple HTML/JavaScript)
**Pages:**
- **Home Page:** Form to submit YouTube URL.
- **Draft View Page:** Displays generated draft and score.

## 4. Simplified Workflow
1. User submits YouTube link.
2. Transcription Agent processes the video.
3. Drafting Agent creates initial draft.
4. Review Agent evaluates the draft and provides a score.

## 5. Minimal API Endpoints
- **POST /api/process:** Submit YouTube URL for processing.
- **GET /api/draft/{id}:** Retrieve generated draft and score.

## 6. Basic Database Schema (SQLite)



6. Basic Database Schema (SQLite)
```sql

CREATE TABLE drafts (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    youtube_url TEXT NOT NULL,
    transcription TEXT NOT NULL,
    draft_content TEXT NOT NULL,
    score FLOAT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## 7. User Interface
### 7.1 Home Page
- Simple form with YouTube URL input and submit button.

### 7.2 Draft View Page
- Display original YouTube URL.
- Show generated draft content.
- Display review score.

## 8. Testing Process
- Set up the prototype environment.
- Implement the basic backend with FastAPI and Crew AI.
- Create a simple frontend with HTML and JavaScript.
- Test the following scenarios:
  a. Submit various YouTube URLs (short videos, long videos, different topics).
  b. Verify transcription retrieval.
  c. Check draft generation quality.
  d. Assess review scores for consistency.

## 9. Success Criteria
- The system can successfully retrieve transcriptions from YouTube videos.
- AI agents can generate readable drafts based on transcriptions.
- The review agent provides consistent scoring.
- The entire process completes within a reasonable timeframe (e.g., under 5 minutes for a 10-minute video).
- Generated drafts show coherence and relevance to the original video content.

## 10. Implementation Steps
- Set up a new Python project with FastAPI and Crew AI.
- Implement the YouTube API service for transcription retrieval.
- Create the Transcription, Drafting, and Review agents using Crew AI.
- Set up a simple SQLite database and implement basic CRUD operations.
- Create API endpoints for processing requests and retrieving drafts.
- Develop a basic HTML/JavaScript frontend for user interaction.
- Implement error handling for common issues (e.g., invalid YouTube URLs, API failures).
- Conduct thorough testing with various YouTube videos.
- Document findings, challenges, and areas for improvement.