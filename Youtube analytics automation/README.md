# YouTube / Lead Analyst Workflow (n8n)

This repository contains an **n8n workflow** that automates the processing of new leads and inquiries (such as those coming from YouTube campaigns or websites).  
The workflow leverages **AI (Google Gemini)** + **Google Sheets/Docs integration** to automatically analyze inquiries, identify responsible contacts, and draft professional email notifications.

---

## 🚀 Features

- **Webhook Trigger**: Captures new lead data (e.g., from ERPNext or website forms).
- **Lead Filtering**: Processes only valid inquiries (`Source = Website` and `Status = Open`).
- **Data Formatting**: Normalizes incoming lead data (name, company, city, country, notes, etc.).
- **AI-Powered Analysis**:
  - Summarizes customer inquiry using Google Gemini LLM.
  - Classifies valid vs invalid leads.
  - Identifies relevant product/service categories.
- **Google Sheets + Docs Integration**:
  - Looks up abbreviations, company policies, and product ownership.
  - Cross-references company contacts to find the right recipient(s).
- **Email Generation**:
  - Creates a professional email body (plain text → HTML).
  - Extracts subject, body, and recipient fields.
  - Prepares email for delivery through Outlook (or any email node).
- **Invalid Leads Handling**:
  - Flags non-relevant inquiries with `"Invalid Lead - Not related to products, services, or solutions."`

---

## 🛠 Tech Stack

- [n8n](https://n8n.io) (workflow automation platform)
- **Google Gemini (PaLM API)** for AI-driven lead analysis
- Google Sheets & Google Docs (company data, policies, and contacts)
- ERPNext Webhooks (lead capture trigger)
- Outlook / Email node (for notifications)

---

## 📂 Workflow Overview

1. **Webhook** receives new lead from ERPNext.  
2. **Filter** only open website-based leads.  
3. **Format Lead Data** into structured fields.  
4. **Check for Notes** → ensure inquiry has content.  
5. **AI Agent** (Gemini-powered) analyzes inquiry:
   - Extracts customer info.
   - Summarizes request.
   - Identifies responsible team/contacts.  
6. **Validation Check**:
   - If valid → prepare email fields (to, subject, body).
   - If invalid → mark lead as ignored.  
7. **Generate Email Body**:
   - Convert plain text → HTML for professional formatting.  
8. **Send Email** via Outlook or other integrations.  

---

## 📸 Visual Flow (Simplified)

```mermaid
flowchart TD
    A[Webhook Trigger] --> B[Filter Lead Source/Status]
    B --> C[Format Lead Data]
    C --> D{Has Notes?}
    D -->|Yes| E[AI Agent Analysis]
    E --> F{Valid Inquiry?}
    F -->|Yes| G[Prepare Email Fields]
    G --> H[Convert to HTML]
    H --> I[Send Email]
    F -->|No| J[Invalid Lead Message]
