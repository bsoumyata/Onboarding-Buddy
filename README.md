# Onboarding Buddy: AI-powered assistant for new hires

A lightweight onboarding assistant that gives new hires a clear checklist and answers policy/benefits FAQs. Built as a PM-focused, low-code prototype: Lovable for the UI and n8n for workflow/LLM logic.

## TL;DR
- **Problem**  
  The first week at a new job is overwhelming for employees and repetitive for HR.  
  New hires juggle multiple setup tasks and policies, while HR spends hours answering FAQs.  

- **Solution**  
  A simple onboarding assistant with:  
  1. **Checklist** – clear, step-by-step tasks for new hires  
  2. **AI chatbot** – instant answers to policy & benefits FAQs  

- **My Role**  
  Defined the problem, wrote the PRD, designed wireframes in Figma, built the prototype in Lovable,  
  and automated workflows in n8n with OpenAI.  


## 🔗 Quick links
- [Live prototype (Lovable)](https://onboarding-buddy-soumyata.lovable.app/)  
- [Product Requirements Document (PRD)](https://www.notion.so/Product-Requirements-Document-PRD-Onboarding-Buddy-25dcb22aeb8280b19d59d4fd95606e11?source=copy_link)  
- [Wireframes (Figma)](https://www.figma.com/design/j8VQerfPU3cIowSJW3TZzq/Onboarding-Buddy?node-id=0-1&t=E9y8lNm8r67tWDgk-1)  
- [n8n workflow export](https://drive.google.com/file/d/1uyVoLT6OyF4MCFoVbcVJ0gu-Nk2X_ISY/view?usp=sharing)  
- [Demo video (Loom)](https://www.loom.com/share/870fcc4f5ee1403cb1dfd697445834c7?sid=f8714863-00cb-4223-9e4a-70bb63a6c6c4)  


## 🚀 Core features
1) **Onboarding checklist**  
   - 3–4 essential setup tasks with short descriptions and direct links.

2) **AI chat assistant**  
   - Answers common HR/benefits/policy questions from a curated knowledge base.  
   - Guardrails:
     - If HR-related but unknown → hands off to HR email.
     - If not HR-related → politely declines.


## 👩‍💻 Who it’s for
- **Primary:** New hires in week 1.
- **Secondary:** HR teams looking to reduce repetitive questions.


## 🌱 Outcomes I’m targeting
- ≥ 90% checklist completion in week 1  
- ≥ 80% FAQ resolution without HR escalation  
- Avg. first-week satisfaction ≥ 4/5  
- Lower “time to productivity” on required setup tasks


## 🛠️ How it works (architecture)
- **Frontend:** Lovable (no-code UI)  
- **Workflow/logic:** n8n  
- **LLM:** OpenAI Chat Model  
- **Knowledge base:** Notion (mock knowledge base for POC)

**High level flow**
1. UI sends question → **n8n Webhook**
2. **n8n AI Agent**:
   - Uses OpenAI for response
   - Pulls policy/benefits info from Notion
   - Keeps short-term context (“memory”)
3. **Format response** → return to UI

> Note: In production, the knowledge base would point to the company’s sources (HRIS, policy hub, benefits portal). No live company data is used here.


## 📸 Screens & assets
See `/assets/` for screenshots:
- `landing.png` — home/hero with sample prompts
- `checklist.png` — essential tasks list
- `chat.png` — policy/benefits Q&A

> Tip: Add a short GIF of the chat flow (`chat-demo.gif`) to make the repo skimmable.


## 🔧 Run notes (for reviewers)
- Lovable UI is live via the link above.  
- The chatbot endpoint was run locally via n8n for the demo.  
- If you want to import the workflow, use the JSON in `/workflow/` and set:
  - `OPENAI_API_KEY` (n8n credentials)
  - Notion credentials & DB IDs (for the mock KB)


## 🤝 Credits
- Built by **Soumyata Binani** (Product Management)  
- Tools: Lovable, n8n, Notion, OpenAI API, Figma


## ⚖️ License
Personal portfolio project. All rights reserved.
