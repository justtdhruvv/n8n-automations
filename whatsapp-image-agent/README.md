# 🖼️ Image Agent – n8n Workflow  

## 📌 Overview  
The **Image Agent Workflow** is an advanced **AI-powered automation pipeline** built in [n8n](https://n8n.io/).  
It allows users to:  
- Generate **new AI images** from text prompts.  
- **Edit existing images** with precise instructions.  
- **Merge two images** into a single coherent concept.  
- Analyze uploaded images and produce **highly accurate scene descriptions**.  
- Automatically **upload and manage files on Cloudinary**.  
- Store interaction history in **PostgreSQL**.  
- Deliver results directly via **WhatsApp messaging**.  

This workflow is designed for **creative assistants, automation developers, and AI image enthusiasts** who want a **plug-and-play multi-modal image generation pipeline**.  

---

## ⚙️ Features  
- 🎨 **New Image Creation** – Convert user text into detailed prompts for hyper-realistic image generation.  
- ✂️ **Image Editing** – Apply user edits while preserving the original subject, lighting, and composition.  
- 🔗 **Image Merging** – Blend two prior images into one unified scene with artistic balance.  
- 👁️ **Image Analysis** – Extract detailed visual descriptions (colors, textures, mood, style, etc.) from images.  
- ☁️ **Cloud Storage** – Seamless Cloudinary integration for secure image hosting.  
- 💾 **Database Logging** – Store chats, prompts, and image URLs in PostgreSQL for history tracking.  
- 📲 **WhatsApp Delivery** – Final results are pushed directly to the user’s WhatsApp.  
- 🎙️ **Voice-to-Prompt** – Audio inputs are transcribed with Whisper and transformed into AI prompts.  

---

## 🛠️ Tech Stack  
- **[n8n](https://n8n.io/)** – Workflow automation  
- **Google Gemini (PaLM API via OpenRouter)** – AI text + image prompt generation  
- **Cloudinary** – Image storage and delivery  
- **PostgreSQL** – Chat and media history  
- **Hugging Face Whisper** – Audio transcription  
- **WhatsApp API** – Message delivery  

---

## 🚀 How It Works  
1. User sends a **text, image, or voice input** via webhook/WhatsApp.  
2. Workflow checks if the request is for:  
   - New image  
   - Image edit  
   - Image merge  
   - Audio-to-text prompt  
3. The system processes input with **Gemini AI + Whisper**, builds a refined image prompt, and calls the **OpenRouter API** for generation.  
4. Output images are uploaded to **Cloudinary**.  
5. Image URLs + metadata are saved in **PostgreSQL**.  
6. Final results are **sent back to the user via WhatsApp**.  

---

## 📦 Setup  

### Prerequisites  
- n8n (self-hosted or cloud)  
- Cloudinary account  
- PostgreSQL database  
- OpenRouter API key (Gemini access)  
- Hugging Face token (Whisper ASR)  
- WhatsApp API credentials  

### Installation  
1. Import the workflow JSON (`image agent.json`) into n8n.  
2. Configure credentials for:  
   - Cloudinary  
   - PostgreSQL  
   - OpenRouter (Gemini)  
   - Hugging Face (Whisper)  
   - WhatsApp API provider  
3. Activate the workflow.  

---

## 🔮 Use Cases  
- AI-powered **WhatsApp image bot**  
- Automated **image editing assistant**  
- **Creative concept generator** for designers  
- Visual storytelling and mood-board builder  
- Educational tool for **art + AI fusion**  

---

## 📜 License  
This project is released under the **MIT License**. Feel free to fork, modify, and use it in your own projects.  
