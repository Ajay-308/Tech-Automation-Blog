# 📚 Tech Blog Automation (n8n Workflow)

## 🚀 Overview
This project automates the process of staying updated with the latest **AI, System Design, and Backend** blogs.  
It scrapes articles from RSS feeds, filters them using keywords + language detection, and emails a styled summary directly to your inbox.

## 🛠 Tech Stack
- [n8n](https://n8n.io/) – workflow automation
- JavaScript Code Node – filtering & sorting
- Gmail API – email delivery
- RSS Feeds – Medium (AI), Dev.to (System Design)

## ⚡ Features
- Scheduled trigger (runs daily/weekly)  
- Filters articles with keywords: `system design, ai, backend, architecture`  
- Ensures English-only content  
- Sends top 2 recent posts with:
  - Title
  - Link
  - Snippet summary
  - Clean HTML email design

## 📸 Example Output
**Subject:** New Tech Blog: *System Design: Jitter Time for Highly Concurrent API*  
**Body:**  
- 📚 Tech Blog Update  
- 📝 Summary: *"Jitter time is a random delay introduced to balance concurrent requests..."*  
- 🔗 [Read Full Article](https://example.com/article)  

## 📂 Usage
1. Import `My workflow.json` into n8n.
2. Connect your Gmail credentials.
3. Activate the workflow — done ✅.

## 👨‍💻 Author
Ajay Singh 
- [GitHub](https://github.com/Ajay-308)  
- [LinkedIn](https://linkedin.com/in/ajay-b94a13233)  
