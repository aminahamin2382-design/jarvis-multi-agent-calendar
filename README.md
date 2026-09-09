# Jarvis AI: Multi-Agent Router & Google Calendar Manager

**Introduction**
Hello, my name is Aminah Amin. I am an undergraduate Computer Science student and the founder of an independent digital consultancy specializing in database automation, e-commerce strategy, and AI integrations. Welcome to my project portfolio.

In this repository, I am showcasing an advanced multi-agent automation architecture built using **n8n**. Instead of relying on a single monolithic prompt, this system implements a master-router pattern where a primary AI conversational agent dynamically handles chat communication and delegates scheduling tasks to an isolated calendar sub-agent.

---

### System Architecture & Workflow Flow

This architecture divides responsibilities cleanly across two connected workflows:

#### 1. Jarvis Main Router (Master Agent)
![Jarvis Main Router](Screenshot%202026-08-26%20013255.png)
* **Chat Interface Trigger:** Listens directly to incoming user chat messages, enabling fluid conversational interactions in plain English.
* **Contextual Memory:** Uses a 'Simple Memory' node to retain conversation history across multiple turns.
* **Tool Delegation:** The core AI Agent evaluates user intent and triggers a custom tool (`Call 'Jarvis Sub-Agent: Calendar'`) whenever a calendar event or meeting needs to be booked.

#### 2. Calendar Sub-Agent
![Calendar Sub-Agent](Screenshot%202026-08-30%20152921.png)

* **Sub-Workflow Execution:** Triggered securely via the "When Executed by Another Workflow" node, functioning as an independent micro-service called by the Main Router.
* **Google Calendar API Integration:** Utilizes an AI Agent powered by an OpenAI Chat Model to parse scheduling details (such as title, start time, and end time) and automatically create the event inside Google Calendar.

---

### Technical Highlights & Business Impact

* **Modular Scalability:** Separating the master chat router from specific execution tools keeps the codebase clean, easily debuggable, and ready for scaling with additional sub-agents (like CRM or email management).
* **Frictionless Executive Scheduling:** Eliminates manual calendar cross-checking, app-switching, and formatting errors.
* **Natural Language Operations:** Empowers business owners and clients to manage their entire calendars simply by chatting naturally with an autonomous assistant.
