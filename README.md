# Job Application Generator

An AI-powered tool for automatically tailoring resumes and writing cover letters for specific job postings. A single HTML file with no dependencies — open it in a browser and it just works.

![Material Design 3](https://img.shields.io/badge/Material_Design-3-6750A4?style=flat-square)
![Vanilla HTML](https://img.shields.io/badge/Vanilla-HTML%2FCSS%2FJS-E34F26?style=flat-square)
![Multiple AI Providers](https://img.shields.io/badge/AI-Groq%2FOpenRouter%2FCloudflare-412991?style=flat-square)

[Описание на русском](README.ru.md)

## How it works

1. Paste the job description
2. Click **Generate**
3. AI adapts the resume to the job requirements and writes a cover letter
4. Each result is automatically checked for hallucinations with a percentage score

Prompts are built-in templates — edit them in the code if you need to customize the logic or output format.

## Stack

- **Vanilla HTML/CSS/JS** — single file, no frameworks or build tools (2042 lines)
- **Material Design 3** — 32 CSS variables, surface tint elevation, shimmer skeleton loading
- **Multiple AI providers:**
  - **Groq** — Llama 3.3 70B (powerful) or 3.1 8B (fast)
  - **OpenRouter** — Llama 3.3, DeepSeek V3, Qwen 2.5 (all free)
  - **Cloudflare AI** — Llama 3.1 8B or 3 8B (built into Workers)
- **localStorage** — API keys, theme preference, saved resumes, history

## Project structure

\`\`\`
job-generator/
└── job-generator.html   — the entire tool in a single file
\`\`\`

## Setup

1. Open \`job-generator.html\` in a browser
2. Choose your AI provider from the settings:
   - **Groq** — free tier, fast (Llama 3.3 70B or 3.1 8B)
   - **OpenRouter** — 3 free models (Llama 3.3, DeepSeek V3, Qwen 2.5)
   - **Cloudflare Workers AI** — requires account ID and API key (Llama 3.1 or 3)
3. Enter your API key for the chosen provider
4. Load or paste a resume in the modal (or select from saved ones)
5. Add job description and click **Generate**

## Deploy to VPS

\`\`\`bash
scp job-generator.html user@server:/var/www/html/job-generator.html
\`\`\`

## Features

- **Parallel generation** of resume and cover letter in a single API request
- **Automatic hallucination detection** (PASSED ✅ / FAILED ❌ + confidence %)
- **Shimmer skeleton** during loading (smooth loading animation)
- **Light and dark theme** with localStorage persistence
- **Keyboard shortcuts:**
  - **Cmd+Enter** (Mac) or **Ctrl+Enter** (Windows) — quick generate
- **Copy clean text** without verification blocks
- **Resume Bank** — save variants to localStorage without file uploads
- **CSV Export** — download history for Google Sheets/Excel
- **Generation history** — track all created resumes and letters
- **Responsive design** — works on mobile and desktop

## Resume Bank (v2 Feature)

Save and manage multiple resume variants without uploading files:

1. Type or paste your resume text in the modal
2. The save button appears automatically when text exceeds 10 characters
3. Click **💾 Save Resume** to save the variant
4. Saved resumes appear in the resume dropdown for quick selection
5. All variants are stored in browser localStorage — persists across sessions

**Use case:** Keep multiple resume versions (generic, tech-focused, leadership-focused) and quickly switch between them.

## CSV Export (v2 Feature)

Export your generation history to CSV format for backup and analysis:

1. Click **⬆️ Export to Sheets** button in the history panel
2. A CSV file downloads with columns: Date, Time, Company, Industry, AI Model, Resume, Letter
3. Open the file in Google Sheets, Excel, or any spreadsheet app
4. All text is properly escaped — special characters (quotes, commas) are handled correctly

**Use case:** Track job applications, analyze which prompts work best, create reports for job search progress.

## Author

[Sasha Arbatsky](https://xn--80aagffumg6aqm6m.xn--p1ai:8443) — UX/UI Designer
