# AI Opportunity Scout(Buddy) : An Autonomous Agent for Students
An autonomous AI agent that finds and processes job opportunities for students.
# AI Opportunity Scout: An Autonomous Agent for Students 

## 🎯 The Mission
The journey from student to professional is filled with opportunities: internships, hackathons, and entry-level jobs. The problem? These opportunities are scattered across dozens of company portals, complex job boards like LinkedIn, and countless newsletters.

This chaos forces students to spend hours on tedious research instead of on learning and applying. We built the AI Opportunity Scout to solve this. Our mission is to **eliminate the manual hustle** by creating a proactive AI agent that finds, understands, and delivers personalized opportunities directly to the user.

## 🤖 The Proof-of-Concept (Our Hackathon MVP)
Building a full-scale, resilient web scraper that can handle dozens of constantly changing websites is a massive engineering challenge—far beyond the scope of a hackathon. A scraper built today could be broken by the time of judging.

Therefore, we made a strategic decision to build a **robust proof-of-concept**. We focused on creating the most critical and complex part of the system: the **intelligent processing core**.

This workflow demonstrates the "brain" of our agent. We use a mock database (in Airtable) to prove that our agent can flawlessly:
1.  Ingest messy, unstructured data.
2.  Use the `gpt-oss-120b` model to understand it.
3.  Enrich it with valuable insights (like urgency).
4.  Triage it based on relevance (e.g., filtering out "Senior" roles).
5.  Deliver clean, actionable notifications.

This MVP proves our core logic is sound and ready to be connected to any data source in the future.

## 🌟 Key Features
* **Fully Autonomous:** The workflow runs automatically on a schedule, checking for new information without any user input.
* **Intelligent Understanding:** Leverages `gpt-oss-120b` to accurately parse unstructured text into structured fields (Title, Company, Deadline, etc.).
* **Smart Triaging:** Automatically identifies and filters out irrelevant opportunities, ensuring the user only sees what matters to them.
* **Urgency Calculation:** Dynamically determines the urgency of an application based on its deadline, helping users prioritize.
* **Personalized Notifications:** Sends a unique, detailed email for every single relevant opportunity, ensuring nothing is missed.

## 🛠️ Tech Stack
* **Automation Platform:** n8n.io
* **Database:** Airtable
* **AI Model:** `gpt-oss-120b` (via Groq API)
* **Notifications:** Gmail

## ⚙️ How to Run This Workflow

This project is an n8n workflow. To test it, you would need to:
1.  Set up a free n8n cloud account or self-host n8n.
2.  Download the `My workflow (1).json` file from this repository.
3.  Import the workflow into your n8n instance.
4.  Create three credentials within n8n:
    * An Airtable credential.
    * A Groq API credential for the AI model.
    * A Gmail credential for notifications.
5.  Create an Airtable base with the same structure as shown in the screenshots and populate it with some sample data.
6.  Activate the workflow and run it manually to see the results.
 
## 🧠 The Agent's Brain: A Visual Workflow
We designed our agent's logic visually using n8n to ensure a clear and powerful flow. 
The screenshot below shows the complete end-to-end process, from fetching raw data to sending intelligent notifications.

`![AI Scout Workflow Diagram](https://github.com/user-attachments/assets/2c992fa7-0979-4e6c-8170-361145a3dac7) '

This architecture is not just a simple script; it's a complete system that includes:
* **Parallel Processing:** The `If` node creates two separate branches to handle "Senior" level jobs and student-level opportunities differently.
* **Data Enrichment:** A custom code node calculates the urgency based on the application deadline, adding a critical piece of information.
* **Clean Logic Flow:** The two branches are merged back together before a final `If` node filters the data, ensuring notifications are only sent for the 11 relevant items. This "Merge, then Filter" pattern is a robust design for clean data handling.

## 📊 The Results: From Chaos to Clarity
Our agent's effectiveness is best shown with a "before and after" of our database.

**Before: The Raw, Messy Data Input**
 `![Before Data Screenshot](https://github.com/user-attachments/assets/0bf4691b-5fa0-400f-ab8b-3ad0fb69829a)'

**After: The Clean, Structured, and Actionable Output**
 `![After Data Screenshot](https://github.com/user-attachments/assets/6468ae6f-5721-4833-8cdc-fe9eb41d9f3e)'



## 🔮 Future Vision
With this intelligent core successfully built, the next steps are to:
* Integrate live data scrapers for specific company career pages and job boards.
* Add user-specific filters, allowing students to get notifications for roles like "Software Engineer," "Cybersecurity Analyst," or "Data Analyst."
* Develop a simple front-end for users to manage their preferences.

---
