🤖 Salesforce Approval Processes AI Agent
Welcome to the Salesforce Approval Processes AI Agent project!
This agent is designed to help you explore and understand Salesforce approval flows and metadata using AI — with support from BigQuery and automation via Make.

📚 Table of Contents
📁 Project Structure

🧰 Requirements

🛠 How to Build the Agent

🧠 Agent Architecture (Mermaid Diagram)

📌 Notes & Tips

📁 Project Structure
text
Copy
Edit
├── AI4SF - Get Approval Processes Metadata From Github.blueprint.json
├── AI4SF - Get BigQuery Data for AI Agent.blueprint.json
├── BigQuery_Approval_Processes_Table_Schema.json
├── approval_processes_tags_explained.avro
├── extractObject.js
├── PROMPT_approval_processes.txt
🧰 Requirements
✅ BigQuery account

✅ Make (Enterprise plan)

✅ Git repository containing Salesforce metadata

✅ Required keys and tokens:

API URL to Git repository

API token

BigQuery service account or connection

🛠 How to Build the Agent
1. Set Up BigQuery Tables
A. Create approval_processes table
Create a new dataset and table in BigQuery

Table name: approval_processes

Schema: Use "Edit as text" → Paste contents of BigQuery_Approval_Processes_Table_Schema.json

B. Create approval_processes_tags_explained table
Create table → Upload approval_processes_tags_explained.avro

Format: AVRO

Table name: approval_processes_tags_explained

2. Import the ETL Scenario in Make
Create new scenario → Import AI4SF - Get Approval Processes Metadata From Github.blueprint.json

Create a function named extractObject → paste content from extractObject.js

Connect all modules according to instructions

Set to "On Demand" and run once to populate BigQuery

3. Configure the Agent
Import AI4SF - Get BigQuery Data for AI Agent.blueprint.json in a new Make scenario

Connect your BigQuery dataset

Choose “Map” for table selection and leave it empty

Create a new agent (ChatGPT, custom UI, etc.)

Paste contents of PROMPT_approval_processes.txt as the agent prompt

Connect the helper Make automation (API integration)

4. Use the Agent!
The agent is now ready to answer questions and analyze your approval processes.

🧠 Agent Architecture (Mermaid Diagram)
mermaid
graph TD
    A[GitHub Repository<br>(Approval Processes Metadata)] --> B[Make Scenario:<br>Extract Metadata]
    B --> C[extractObject.js<br>Custom Function]
    C --> D[BigQuery Table:<br>approval_processes]

    E[approval_processes_tags_explained.avro] --> F[BigQuery Table:<br>approval_processes_tags_explained]

    D & F --> G[Make Scenario:<br>Get BigQuery Data for Agent]
    G --> H[AI Agent<br>(ChatGPT / Custom Agent)]
📌 Notes & Tips
🧪 This agent is still under development. You may receive incomplete or imperfect responses.

🧠 The most important component is the prompt — tune it for best results.

💬 Feedback is welcome — contribute to improving the assistant!

Let me know if you'd like:

A live badge section (GitHub actions, etc.)

A dark mode–friendly Mermaid style

Auto-linking to the actual blueprint files in your repo.
