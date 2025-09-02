# WhatsApp Lead Outreach and Reminder Automation

## Overview

This project is an end-to-end WhatsApp automation system built for a real estate agent in my professional circle. The goal was to streamline lead management, follow-up, and communication using automation and AI—helping the agent focus on closing deals, not chasing messages. The system uses headless browser automation to interact directly with the WhatsApp Web UI, enabling reliable message delivery and workflow control without having to rely on the WhatsApp Business API.

## Features

- **Automated lead intake and storage** (Airtable integration)
- **Personalized WhatsApp messaging** (using AI-generated drafts for first contact and follow-ups)
     - The AI generates the messages based on
          - The lead information: firstName, lastName, emailAddress, phoneNumber, campaignName
          - three main frameworks: Concierge Assist, Curated Match, Position & Offer
          - additionally the brand guidelines for the real estate agents are considered
- **Human-in-the-loop approvals** (agent can review and approve message drafts before sending)
- **Automated follow-up logic** (context aware reminders at 24h/72h/7d intervals if no reply)
- **Reply detection and push notification** (see below for details)
- **Full auditability and data tracking** (all inbound and outbound WhatsApp messages stored in Supabase/Postgres backend)
- **Scheduled data cleanup** (Supabase runs a scheduled job every 30 minutes to clear out messages not from leads)

## Stack & Tools

- n8n (workflow orchestration)
- Airtable (lead database)
- WhatsApp headless browser API (messaging)
- LLMs for message drafting (e.g., OpenAI, custom prompt logic—redacted)
- **Supabase/Postgres** (back end for storing all message logs and state)
- Push notification service (e.g., Pushover)

## Architecture

1. **Lead intake:** New leads are added to Airtable, triggering the workflow
2. **Message draft:** The system generates a personalized WhatsApp message draft for the agent
3. **Agent approval:** The agent reviews/edits the draft (human-in-the-loop)
4. **Message send:** Once approved, the message is sent via WhatsApp headless browser API
5. **Follow-up logic:** If no reply, follow-ups are automatically drafted and scheduled at set intervals
6. **Reply detection:**  
   - All inbound and outbound WhatsApp messages are stored in Supabase  
   - A scheduled flow in Supabase runs every 30 minutes to clear messages not associated with leads (keeps the DB clean and focused)
   - When a lead replies, Supabase sends a webhook to n8n, which triggers a push notification to the agent and removes the lead from the follow-up flow
7. **Notification:** Agent receives real-time push notifications through Pushover API when a lead replies or requires manual action

## Demo / How it Works

For a sanitized demo, see the included `whatsapp-lead-automation-sanitized.json` and sample screenshots/diagrams. API keys, prompt logic, and personalized data has been redacted as the system is currently in PROD.

If you’d like a technical walkthrough feel free to reach out.

## Outcomes

- Reduced manual message drafting and follow-up effort by over 80%
- Faster response times and better lead engagement for the agent
- System is now live and used for real-world sales outreach
- Cool Airtable interface that acts as a micro CRM


Laith Mufti  
[LinkedIn](https://www.linkedin.com/in/laith-mufti) | lysmufti@gmail.com
