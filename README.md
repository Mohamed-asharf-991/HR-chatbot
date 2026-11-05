HR Automation System

An end-to-end HR system built with n8n, Google Workspace and an LLM. HR opens and closes positions without touching the automation, candidates and employee referrals are screened by AI, and the strongest candidates are sent to HR automatically.

Live portal: [https://mohamed-asharf-991.github.io/HR-chatbot/]

Built as part of a training assignment. The goal was an HR system that handles the whole flow, from opening a position to alerting HR about a strong candidate.

What it does
HR opens or closes a position through one Google Form. Each new position gets a unique Job ID and pre-filled application and referral links, and HR receives them by email.
Candidates apply through an external application form or an employee referral form. Both go through the same screening workflow.
AI screens every CV: it extracts the candidate's details, scores the match from 0 to 100 against the job requirements, and assigns a priority (High, Medium, Low).
Results are saved in Google Sheets with the CV stored in Google Drive. High-priority candidates trigger an email to HR with the summary and the CV link.
The employee portal lists the open positions automatically, so nothing has to be edited when jobs open or close.
An HR chatbot answers company policy questions using RAG (Qdrant vector search).
Screenshots
Opening a position

Workflow A: position management

HR receives the Job ID and both links by email:

Email: position opened

Closing a position

Email: position closed

Applications that arrive for a closed position are ignored, and the applicant is told the position is closed.

CV screening

Workflow B: CV screening

High-priority candidate alert

Email: strong candidate

Employee portal

The page fetches the open positions from an n8n webhook, so new jobs appear and closed jobs disappear without any code change.

Portal with open positions

Workflow C: jobs webhook

HR chatbot (RAG)

RAG chatbot workflow

Tech stack
Automation: n8n (webhooks, Google Sheets, Google Drive, Gmail, Code nodes)
Forms and data: Google Forms, Google Sheets, Google Drive
AI: an LLM for CV information extraction and scoring, Qdrant for RAG
Frontend: HTML, CSS and JavaScript hosted on GitHub Pages
Repository structure
index.html: the HR portal (chatbot and open positions)
workflows/: exported n8n workflows (JSON)
screenshots/: images used in this README
Notes
The data in the screenshots is sample data.
The n8n workflows can be imported from the workflows/ folder. Credentials and form links need to be reconnected on import.
