# 🔍 Lead Generation Scraper with LinkedIn – n8n Workflow

This repository contains an **n8n workflow** that automates the process of discovering, scraping, and analyzing business leads from Google search results.  
Unlike the non-LinkedIn version, this workflow includes a **LinkedIn scraping branch** that extracts detailed company insights directly from LinkedIn pages.

---

## ✨ Features

- **Google Search Automation**
  - Uses [Serper API](https://serper.dev) to perform Google searches for a given query.
  - Captures the top 50 organic results.

- **Lead Normalization & Filtering**
  - Cleans raw company names and website URLs.
  - Filters out junk results (directories, review sites, job boards, etc.).
  - Produces a clean list of valid company websites.

- **Homepage Scraping & AI Analysis**
  - Scrapes company websites using [ScraperAPI](https://www.scraperapi.com).
  - AI Agent analyzes homepage HTML for:
    - Contact links (About, Careers, Contact, etc.)
    - Email addresses and phone numbers
    - Social media links

- **Deep Scan**
  - Follows contact-related internal links (Contact/About/Careers).
  - Specialized AI agent extracts:
    - Verified emails
    - Phone numbers
    - Contact form presence

- **LinkedIn Integration**
  - Detects LinkedIn company profile links from the homepage scan.
  - Extracts structured company data via LinkedIn API (ScrapingDog + AI).
  - Retrieves:
    - Company summary
    - Employee count
    - Industry
    - Headquarters
    - Contact details

- **Data Aggregation**
  - Combines findings from homepage, internal scans, and LinkedIn.
  - Deduplicates emails and phone numbers.
  - Outputs one clean JSON object per company lead.

---

## 🛠️ Tech Stack

- [n8n](https://n8n.io) – workflow automation platform  
- [Serper API](https://serper.dev) – Google search results  
- [ScraperAPI](https://www.scraperapi.com) – website HTML extraction  
- [ScrapingDog](https://scrapingdog.com) – LinkedIn scraping  
- [Google Gemini](https://ai.google.dev) – AI-based data extraction & parsing  

---

## 📂 Workflow Steps

1. **Input Query** – Set the search query (e.g., `"Marketing and Advertising agencies in Canada"`).  
2. **Serper Search** – Fetch search results.  
3. **Parse & Normalize** – Clean results and filter out junk.  
4. **Lead Loop** – Process each company one at a time (with a 1.5s delay).  
5. **Homepage Scraping** – Fetch company website.  
6. **AI Analysis** – Extract links, emails, phones, and social profiles.  
7. **Deep Scan** – Follow internal links for more detailed extraction.  
8. **LinkedIn Scraping** – If LinkedIn link is found, extract structured company details.  
9. **Aggregation** – Merge all findings into a single JSON object.  

---

## 📊 Example Output

```json
{
  "company_name": "XYZ Marketing",
  "website": "https://xyzmarketing.com",
  "emails": ["hello@xyzmarketing.com"],
  "phones": ["+1 416 123 4567"],
  "contact_form_present": true,
  "linkedin_summary": "XYZ Marketing is a Canadian digital agency...",
  "employee_count": "51-200",
  "industry": "Marketing & Advertising",
  "headquarters": "Toronto, Canada",
  "socials": [
    "https://www.linkedin.com/company/xyzmarketing",
    "https://twitter.com/xyzmarketing"
  ]
}
