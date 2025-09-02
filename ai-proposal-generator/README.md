# AI Proposal Generator

## Overview

This project automates end-to-end proposal generation based on structured inputs captured during a discovery or sales call. It was implemented for a friend running an AI automation agency to speed up turnaround from conversation to client-facing proposal. By the end of the call, a proposal with tailored problem framing, solution design, timeline, and pricing is ready to send to the prospect.

## Features

- Multi-stage LLM drafting (Challenge, Solution, Scope, Timeline, Investment)
- Form Trigger with the following fields: firstName, lastName, companyName, problemStatement, timeCost, solutionOffering, scope, howSoon, and price/cost.
- Brand/voice control via stored guidelines
- Output to Google Slides
- Audit trail of inputs and outputs

## Stack & Tools

- n8n (workflow orchestration)
- Typeform/Form Trigger (deal context)
- LLM chaining
- Google Slides (templated document output)

## Architecture

1. **Capture**: Form or call transcript collects context on business pain, goals, solution direction.
2. **Drafting**: LLM generates proposal sections based on structure and tone.
3. **Assembly**: Outputs formatted into Google Slides.
4. **Storage**: Document stored and link recorded in Google Drive.
5. **Delivery**: Slides link is ready to send by end of sales call.
6. **WIP**: Export automatically as PDF -> upload PDF to e-Sign platform -> embed Stripe payments link

## Demo / How it Works

A sanitized workflow (`ai_proposal_generator_redacted`) is included. All prompts, credentials, and sensitive configuration have been replaced with placeholders.

If you’d like a technical walkthrough feel free to reach out.

## Outcomes

- Cuts proposal time from hours to minutes
- Ensures consistent language and structure
- Enables sales agents to close faster with less manual effort
- Higher perceived professionalism

Laith Mufti  
[LinkedIn](https://www.linkedin.com/in/laith-mufti) | lysmufti@gmail.com
