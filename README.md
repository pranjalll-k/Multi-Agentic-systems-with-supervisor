# Multi-Agentic-systems-with-supervisor 🤖
This repository contains the n8n workflows on how to build a multi-agent AI system with a supervisor agent, worker agents for email, calendar, contacts, and content creation, as well as a custom knowledge base.


<img width="1364" alt="Screenshot 2025-03-23 at 1 50 36 PM" src="https://github.com/user-attachments/assets/a2f3a1ff-6462-4862-932b-63173a9b484e" />


## Project Overview

The project includes the following key components:

*   **Supervisor Agent:** An agent responsible for orchestrating tasks between different worker agents. It can access tools like web search (via Serp API) and delegate tasks based on user input.
*   **Worker Agents:** Specialised agents designed for specific tasks:
    *   **Email Agent:** Capable of sending, reading, and replying to emails (using Gmail).
    *   **Calendar Agent:** Able to create new calendar events and retrieve current calendar entries (using Google Calendar).
    *   **Contact Agent:** Can retrieve contact details (from Google Contacts), create new contacts, and update existing ones.
    *   **Content Creator Agent:** Responsible for generating various forms of written content like research papers, blog posts, and social media updates.
*   **Custom Knowledge Base:** Integration with Pinecone to create and maintain a custom knowledge base, allowing the agents to answer questions based on uploaded documents (like PDFs, CSVs, Word documents).
*   **Memory Management:** Implementation of window buffer memory to enable conversational agents to remember previous interactions.

## Getting Started

To use these workflows, you will need to have n8n installed. Either local installation or using the paid cloud service.

### Prerequisites

*   **n8n Instance:** You need a running instance of n8n, either installed locally or via the cloud service.
*   **API Keys and Credentials:** The workflows rely on several external services and require API keys and credentials. You will need to set up accounts and obtain the following:
    *   **OpenAI API Key:** Required for the AI agent nodes (GPT-4o (mini). Note that OpenAI is a paid service. 
{You can use an opensource LLM like Qwen / Grok for Inference as free alternatives.}
    *   **Serp API Key:** For the Google search tool. You can register for a free API key at serpapi.com.
    *   **Google Credentials:** Required for accessing Gmail and Google Contacts. This involves setting up a Google Cloud project, enabling the Gmail and Google People APIs, and creating OAuth 2.0 client IDs.
    *   **Pinecone API Key:** For the custom knowledge base. You can create a free account at pinecone.io and create an index.

### Installation and Setup

1.  **Install n8n:** Install it locally or sign-up for a cloud trial to set up your n8n instance.
2.  **Download Workflows:** Download the workflow files from this repository.
3.  **Import Workflows:** In your n8n instance, navigate to the workflows page and import the downloaded workflow files (or recreate them). You can import workflows by clicking on the three dots menu and selecting "Import".
4.  **Set up Credentials:** For each service integration (OpenAI, Serp API, Google, Pinecone), you will need to create and configure credentials in n8n.
5.  **(Optional) Upload Knowledge Base Documents:** If you want to use the custom knowledge base, you will need to use the "Update Knowledge Base" workflow to upload your documents to the Pinecone index. You'll need to have your Pinecone credentials and index name configured correctly.

### Using the Workflows

Once the workflows and credentials are set up, you can start interacting with the AI agents. Triggering the supervisor agent via a chat message.

*   **Supervisor Agent:** Activate the "Supervisor Agent" workflow. You can then use the "Open chat" button to send messages to the agent and observe how it delegates tasks to the worker agents.
*   **Worker Agents:** The worker agents ("Email Agent," "Calendar Agent," "Contacts Agent," "Content Creator") are designed to be called by the supervisor agent. You can also test them individually using the "When executed by another workflow" trigger and setting mock data.
*   **Knowledge Base Update:** The "Update Knowledge Base" workflow (or the recreated steps) can be triggered via the form submission to upload documents to your Pinecone index.

## Contributing

If you have improvements or find issues with these workflows, feel free to fork this repository and submit pull requests.
