# 📄 Resume Screening Automation Workflow (n8n)

An automated, AI-powered workflow built in **n8n** that screens resumes received via Gmail, extracts candidate information, compares it against a job description, and logs results into Google Sheets — all without manual effort.

---

## 🚀 Features

- 📥 **Automatic resume intake** from Gmail  
- ☁️ **Upload and store** files in Google Drive  
- 📄 **PDF & DOCX support** with auto-conversion  
- 🔍 **Text extraction** from resumes & job descriptions  
- 🤖 **AI screening using Gemini**  
- 🧠 Structured output with strengths, weaknesses, ratings  
- 📝 **Candidate info extraction** (name + email)  
- 📊 **Google Sheets logging** for tracking candidates  

---

## 🧭 Workflow Overview

### 🔔 1. Gmail Trigger  
Watches for new emails with the keyword **"resume"** and automatically downloads attachments.

### ☁️ 2. Upload File to Google Drive  
Uploads the resume to your Drive for storage and processing.

### 🔀 3. File Type Switch  
Routes the file depending on whether it's a **PDF** or **Word** document.

### 📝 4. Convert Word to Google Docs  
Converts DOCX → Google Docs for text extraction (if needed).

### 📥 5. Download File  
Fetches the PDF or converted Google Doc for processing.

### 📄 6. Extract Text from Resume  
Extracts clean, readable text from the resume.

### 🧹 7. Standardize Extracted Text  
Normalizes the extracted text into a consistent field.

### 📄 8. Download Job Description  
Fetches the stored job description PDF from Google Drive.

### 🧪 9. Extract Text from Job Description  
Extracts job requirements and responsibilities for AI comparison.

### 🤖 10. AI Resume Screening (Gemini)  
Generates a structured screening report including:  
- ⭐ Candidate Strengths  
- ⚠️ Candidate Weaknesses  
- 🔥 Risk Factor  
- 🚀 Reward Factor  
- 🎯 Overall Fit (0–10)  
- 📝 Justification  

### 🧩 11. Structured Output Parser  
Validates and formats the AI output into a clean JSON structure.

### 👤 12. Candidate Information Extractor  
Extracts the candidate’s:  
- First name  
- Last name  
- Email address  

### 📊 13. Append to Google Sheet  
Logs the full evaluation into a tracking sheet including:  
- Date  
- Candidate details  
- Resume link  
- AI analysis & scores  

---

## 🛠 Requirements

- **n8n v1.120.4 or later**  
- Connected accounts:  
  - Gmail OAuth2  
  - Google Drive OAuth2  
  - Google Sheets OAuth2  
  - Google Gemini API  

---

## ⚙️ Customization Options

📝 **Job Description**  
Update the *Get Job Description* node to point to your preferred file.

📊 **Google Sheets Mapping**  
Customize column order inside *Append row*.

🤖 **AI Prompt**  
Modify the system prompt in *Recruiter AI Agent* to match your hiring criteria.

---

## 🔄 How It Works (Simplified Flow)

1. 📩 Resume email received  
2. ☁️ Resume uploaded to Drive  
3. 🔍 File type detected  
4. 🔄 Convert if needed  
5. 📄 Extract resume text  
6. 📄 Extract JD text  
7. 🤖 AI compares both and generates a structured report  
8. 👤 Candidate details extracted  
9. 📊 Everything logged in Sheets  

---

## 🧰 Troubleshooting

❗ **Model output doesn’t match schema**  
- Ensure Structured Output Parser schema matches AI output exactly  
- PDF extraction may produce messy text — consider cleaning it  

🔐 **Google Drive access issues**  
- Re-authenticate credentials  
- Ensure the workflow has write access  

⚠️ **Gemini errors**  
- Simplify the prompt  
- Increase model temperature or switch model version  

---

## 🏆 Credits

Built using:  
- **n8n** ⚙️  
- **Google Workspace** 📁  
- **Gemini AI** 🤖  

---

