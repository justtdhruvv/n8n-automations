# 🚀 Lead Generation Scraper (No LinkedIn) – n8n Workflow

This repository contains an **n8n workflow** designed to automatically scrape, filter, and extract **high-quality business leads** from Google search results **without relying on LinkedIn**.  
The workflow combines **Serper API**, **ScraperAPI**, and **Google Gemini (AI)** to fetch websites, analyze their content, and extract verified contact details.

---

## ✨ Features

- **Google Search Automation**
  - Uses [Serper API](https://serper.dev) to fetch Google results for a given search query.
  - Customizable search term (e.g., `"web designing agency ahmedabad"`).

- **Lead Normalization & Smart Filtering**
  - Cleans company names and website URLs.
  - Filters out junk results like directories (Clutch, DesignRush, GoodFirms), review sites, job listings, and irrelevant domains.

- **Polite Scraping**
  - Sequential batch processing (`1 company at a time`).
  - Waits `1.5 seconds` between requests to avoid blacklisting.

- **Homepage Scraping & AI Analysis**
  - Fetches raw HTML using ScraperAPI.
  - AI Agent scans homepage for:
    - Contact page links
    - About / Careers / Support pages
    - Social media links
    - Visible email addresses and phone numbers

- **Deep Scan Branch**
  - Follows promising internal links (`Contact`, `About`, `Careers`, etc.).
  - Runs a **specialist AI extraction** to pull:
    - Emails
    - Phone numbers
    - Contact forms

- **Data Aggregation**
  - Combines all findings into a single clean JSON object.
  - Removes duplicate emails and phone numbers.
  - Merges extracted data with original company info.

---

## 🛠️ Tech Stack

- [n8n](https://n8n.io) (workflow automation)
- [Serper API](https://serper.dev) (Google Search results)
- [ScraperAPI](https://www.scraperapi.com) (website HTML extraction)
- [Google Gemini](https://ai.google.dev) (AI-based content parsing & data extraction)

---

## 📂 Workflow Overview

```mermaid
flowchart TD
    A[Manual Trigger / Query Input] --> B[Serper Search]
    B --> C[Parse Search Results]
    C --> D[Normalize Leads + Filter Junk]
    D --> E[Loop Over Leads]
    E --> F[Wait (1.5s Delay)]
    F --> G[Fetch Homepage]
    G --> H[AI Agent - Homepage Scan]
    H --> I[Format Output]
    I --> J{Useful Link?}
    J -->|Yes| K[Fetch Internal Page]
    K --> L[AI Agent Deep Scan]
    L --> M[Output Combiner]
    M --> N[Merge Final Results]
    J -->|No| N
    N --> O[Clean JSON Output (Company + Contacts)]
