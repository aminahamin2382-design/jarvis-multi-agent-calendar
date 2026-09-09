# Jarvis AI: Multi-Agent Router & Google Calendar Manager

**Introduction**
Hello, my name is Aminah Amin. I am an undergraduate Computer Science student and the founder of an independent digital consultancy specializing in database automation, e-commerce strategy, and AI integrations. Welcome to my project portfolio.

In this repository, I am showcasing an advanced multi-agent automation architecture built using **n8n**. Instead of relying on a single monolithic prompt, this system implements a master-router pattern where a primary AI conversational agent dynamically delegates specialized tasks (such as calendar management and scheduling) to an isolated sub-agent.

---

### System Architecture & Workflow Flow

This architecture is split into two interconnected workflows:

#### 1. The Jarvis Main Router (Master Agent)
![Jarvis Main Router](Screenshot%202026-08-26%20010344_2.png)

* **Chat Interface:** Operates via a natural language chat trigger, allowing users to converse fluidly in plain English.
* **Conversational Memory:** Equipped with a 'Simple Memory' node to maintain context across multi-turn interactions.
* **Tool Delegation:** Acts as a router that identifies user intent and triggers a custom tool (`Call 'Jarvis Sub-Agent: Calendar'`) when a booking or scheduling request is detected.

#### 2. The Calendar Sub-Agent
![Calendar Sub-Agent](Screenshot%202026-08-30%20152928_2.png)

* **Sub-Workflow Trigger:** Uses the "When Executed by Another Workflow" trigger, meaning it functions as an autonomous micro-service called dynamically by the Main Router.
* **Google Calendar Integration:** Uses an AI Agent powered by an OpenAI Chat Model to parse date, time, and title variables, then directly executes the API call to create the event in Google Calendar.

---

### Technical Highlights & Business Impact

* **Modular AI Scaling:** Separating responsibilities into a main router and a sub-agent keeps the system clean, debuggable, and infinitely expandable (allowing new sub-agents for emails, CRMs, or databases to be plugged in easily).
* **Frictionless Executive Scheduling:** Eliminates app-switching, manual calendar checking, and timezone formatting errors. 
* **Conversational Automation:** Empowers business executives and clients to manage their entire schedules simply by chatting naturally with an AI assistant.
