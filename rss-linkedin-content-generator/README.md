# LinkedIn RSS Content Generator

![Alt text](https://github.com/lymxfti/ai-automation-portfolio/blob/main/rss-linkedin-content-generator/n8n-workflow-screenshot.png)

## Overview

This project automates LinkedIn content creation by sourcing posts from curated RSS feeds, processing them with AI, and generating polished drafts ready for publishing. It was designed to help busy professionals maintain a consistent LinkedIn presence while saving time on manual research and drafting.

## Features

- **RSS Feed Integration**: Collects articles from multiple curated RSS sources.
- **Deduplication Logic**: Filters out duplicates and previously processed articles.
- **AI Summarisation**: Generates concise summaries and insights from sourced content.
- **AI Research**: Researches and enriches each topic through generating queries and focusing on statistics, case studies etc. 
- **Framework-based Drafting**: Uses copywriting frameworks (PAS, IIR, SIA, WSWNW) to produce varied and engaging post styles.
- **Optional Image Generation**: Toggle to mark whether a post needs an image. If selected, the workflow generates an image and uploads it to Airtable, storing the file or URL with the draft.
- **Scheduling**: Stores generated drafts in Airtable for review, approval, and scheduled publishing.

## Stack & Tools

- n8n (workflow orchestration)
- RSS Feeds
- Airtable (draft storage and scheduling)
- LLMs for summarisation and content framing
- Image generation API (sanitized for public sharing)
- API Integrations (sanitized for public sharing)

## Architecture

1. **RSS Collection**: Fetch new articles from curated feeds.
2. **Filter and Deduplicate**: Remove duplicates or outdated entries.
3. **Summary**: AI summurises the articles/blogs for the user to decide if they want to post about it.
4. **Research**: AI generates queries related to statistics, case studies, opinions and quotes and content analysis of the topic. Searches queries through Tavily API and returns results. 
5. **Framing**: AI considers the research results and then generates LinkedIn post drafts using selected frameworks (Problem-Agitate-Solve, Insight-Impact-Recommendation, Story-Insight-Action, What? So What? Now What?).
6. **Image Selection and Generation**: If the draft is flagged as needing an image, generate an image and attach it to the record in Airtable.
7. **Storage**: Save drafts and any generated images into Airtable with metadata for scheduling.
8. **Review and Approval**: Posts can be edited, refined, and approved before publishing.

## Demo / How it Works

A sanitized workflow `linkedin-rss-content-generator-sanitized.json` is included. All API keys, IDs, and URLs have been replaced with placeholders.

If you’d like a technical walkthrough feel free to reach out.

## Outcomes

- Reduces research and drafting effort by up to 90%.
- Enables consistent, high-quality LinkedIn posting.
- Adds visual appeal with optional AI-generated images.
- Frees up time for strategic tasks while maintaining professional visibility.

Laith Mufti  
[LinkedIn](https://www.linkedin.com/in/laith-mufti) | lysmufti@gmail.com
