# Tech Blog Automation


![n8n Workflow](https://img.shields.io/badge/n8n-Workflow-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![RSS](https://img.shields.io/badge/RSS-FFA500?style=for-the-badge&logo=rss&logoColor=white)
![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)

Stay ahead of the curve with automated tech content delivery.

[Features](#features) • [Workflow](#workflow) • [Installation](#installation) • [Usage](#usage) • [Customization](#customization) • [Example-output](#example-output)

---


## Overview
<img width="2542" height="1024" alt="image" src="https://github.com/user-attachments/assets/f92086b7-7109-40c9-b6d5-ec035707ed57" />


An intelligent n8n workflow that automatically curates and delivers the latest AI, System Design, and Backend articles directly to your inbox. Say goodbye to manual RSS feed checking and hello to personalized, filtered tech content.

### What It Does

- Scrapes RSS feeds from Medium, Dev.to, and other tech platforms
- Filters articles using smart keyword matching
- Detects and ensures English-only content
- Delivers formatted summaries to your email
- Automates everything on your schedule

---

## Features

| Feature | Description |
|--------|-------------|
| Smart Filtering | Automatically filters articles by keywords: `system design`, `ai`, `backend`, `architecture`, `scalability` |
| Language Detection | Ensures only English articles make it to your inbox |
| Priority Sorting | Delivers the most recent and relevant content first |
| Clean Emails | Styled HTML emails with snippets and direct links |
| Fully Customizable | Easily modify keywords, sources, and scheduling |
| Secure | Uses Gmail API with OAuth2 authentication |

---

## Workflow

\`\`\`mermaid
graph LR
    A[Schedule Trigger]  B[RSS Read - Medium AI]
    A  C[RSS Read - Dev.to Design]
    B  D[Merge Feeds]
    C  D
    D  E[JavaScript Filter]
    E  F[Send Email]
\`\`\`

### Workflow Stages

1. Schedule Trigger — Runs daily/weekly based on your preference  
2. RSS Read Nodes — Fetch latest articles from configured feeds  
3. Merge — Combine articles from multiple sources  
4. JavaScript Code — Filter by keywords and language, sort by date  
5. Send Message — Deliver top items via Gmail

---

## Tech Stack

- n8n — Workflow automation
- JavaScript — Custom filtering and logic
- RSS Feeds — Content source
- Gmail API — Email delivery via OAuth2

---

## Installation

### Prerequisites

- n8n installed (self-hosted or cloud)
- Gmail account with API access enabled
- Basic understanding of n8n workflows

### Quick Setup

1. Clone or Download the workflow
   - git clone https://github.com/Ajay-308/tech-blog-automation.git
   - cd tech-blog-automation

2. Import into n8n
   - Open the n8n dashboard
   - Click “Import from File”
   - Select `My_workflow.json`

3. Configure Gmail Credentials
   - Go to Credentials → Add New
   - Select Gmail OAuth2
   - Follow the authentication flow

4. Customize (optional)
   - Update RSS feed URLs
   - Modify filter keywords in the JavaScript node
   - Adjust the schedule trigger timing

5. Activate the Workflow
   - Toggle the workflow to Active
   - Test run to verify everything works

---

## Usage

### Automatic Mode
- The workflow runs automatically based on your schedule (for example, daily at 9 AM)

### Manual Mode
- Click “Execute Workflow” in n8n to run immediately

---

## Customization

### Add More RSS Feeds

Add new feed URLs in the RSS Read node (one per line or per node configuration):

\`\`\`
https://medium.com/feed/tag/machine-learning
https://dev.to/feed/tag/kubernetes
\`\`\`

### Modify Filter Keywords

Edit the JavaScript code node:

\`\`\`javascript
const keywords = [
  'system design',
  'ai',
  'backend',
  'architecture',
  'microservices',
  'kubernetes',
  'devops'
];
\`\`\`

### Change the Schedule

Adjust the Schedule Trigger node:
- Daily → Weekly
- Specific time adjustments
- Multiple schedules if needed

---

## Example Output

Subject: New Tech Blog: System Design — Jitter Time for Highly Concurrent APIs

------------------------------------------------------------

Tech Blog Update

Pinned: System Design — Jitter Time for Highly Concurrent APIs  
Jitter time is a random delay introduced to balance concurrent requests and prevent thundering herd problems in distributed systems...

Read Full Article: https://example.com/article-link

(Additional items continue in the same format)

---

## Notes

- Gmail OAuth2 is used for secure authentication. Ensure your credentials are configured properly in n8n.
- If you add many feeds or increase frequency, consider rate limits and quota for your email provider.
- For best results, periodically review and refine your keyword list.

---

## License

This repository is provided under the MIT License. See `LICENSE` if present, or use your preferred license.
