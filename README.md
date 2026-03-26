# Job Application Generator

An AI-powered tool for automatically tailoring resumes and writing cover letters for specific job postings. A single HTML file with no dependencies — open it in a browser and it just works.

![Material Design 3](https://img.shields.io/badge/Material_Design-3-6750A4?style=flat-square)
![Vanilla HTML](https://img.shields.io/badge/Vanilla-HTML%2FCSS%2FJS-E34F26?style=flat-square)
![Notion API](https://img.shields.io/badge/Notion-API-000000?style=flat-square&logo=notion)
![Claude AI](https://img.shields.io/badge/Claude-AI-CC785C?style=flat-square)

[Описание на русском](README.ru.md)

## How it works

1. Paste the job description
2. Click **Generate**
3. AI adapts the resume to the job requirements and writes a cover letter
4. Each result is automatically checked for hallucinations with a percentage score

Prompts are built-in templates — edit them in the code if you need to customize the logic or output format.

## Stack

- **Vanilla HTML/CSS/JS** — single file, no frameworks or build tools
- **Material Design 3** — tokens, surface tint elevation, Extended FAB, shimmer skeleton
- **Multi-provider support** — Groq, OpenRouter, or Cloudflare Workers AI
- **Flexible AI models** — works with any model from supported providers

## Project structure

\`\`\`
job-generator/
└── job-generator.html   — the entire tool in a single file
\`\`\`

## Setup

1. Open \`job-generator.html\` in a browser
2. Choose your AI provider from the settings:
   - **Groq** — free tier, fast inference
   - **OpenRouter** — supports multiple models
   - **Cloudflare Workers AI** — requires account ID and API key
3. Enter your API key for the chosen provider
4. Load or paste a resume, add job description, and click Generate

## Deploy to VPS

\`\`\`bash
scp job-generator.html user@server:/var/www/html/job-generator.html
\`\`\`

## Features

- **Parallel generation** of resume and cover letter in a single request
- **Automatic detection** and parsing of the verification block (PASSED / FAILED + score %)
- **Shimmer skeleton** during loading
- **Light and dark theme** with localStorage persistence
- **Cmd+Enter shortcut** for quick generation
- **Copy button** — copies only the clean text without the verification block
- **Resume Bank** — save multiple resume variants to localStorage for quick access across sessions
- **CSV Export** — download generation history as CSV for easy import to Google Sheets

## Resume Bank (v2 Feature)

Save and manage multiple resume variants without uploading files:

1. Type or paste your resume text in the modal
2. The save button appears automatically when text exceeds 10 characters
3. Click **💾 Сохранить как резюме** to save the variant
4. Saved resumes appear in the resume dropdown for quick selection
5. All variants are stored in browser localStorage — persists across sessions

**Use case:** Keep multiple resume versions (generic, tech-focused, leadership-focused) and quickly switch between them.

## CSV Export (v2 Feature)

Export your generation history to CSV format for backup and analysis:

1. Click **⬆️ В Google Sheets** button in the history panel
2. A CSV file downloads with columns: Date, Time, Company, Industry, AI Model, Resume, Letter
3. Open the file in Google Sheets, Excel, or any spreadsheet app
4. All text is properly escaped — special characters (quotes, commas) are handled correctly

**Use case:** Track job applications, analyze which prompts work best, create reports for job search progress.

## Author

[Sasha Arbatsky](https://xn--80aagffumg6aqm6m.xn--p1ai:8443) — UX/UI Designer
