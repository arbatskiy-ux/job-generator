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
3. Claude adapts the resume to the job requirements and writes a cover letter
4. Each result is automatically checked for hallucinations with a percentage score

Prompts are stored in Notion and fetched on every generation — update the prompt in Notion and the tool picks it up without any code changes.

## Stack

- **Vanilla HTML/CSS/JS** — single file, no frameworks or build tools
- **Material Design 3** — tokens, surface tint elevation, Extended FAB, shimmer skeleton
- **Claude API** (claude-sonnet-4) — parallel generation of resume and cover letter
- **Notion API** — system prompt storage, fetched on every request

## Project structure

\`\`\`
job-generator/
└── job-generator.html   — the entire tool in a single file
\`\`\`

## Setup

1. Open \`job-generator.html\` in any text editor
2. Find the constants at the top of the script and insert your keys:

\`\`\`js
const CLAUDE_KEY = 'sk-ant-...';
const NOTION_KEY = 'secret_...';
const NOTION_RESUME_ID = '...';
const NOTION_LETTER_ID = '...';
\`\`\`

3. Open the file in a browser or deploy to a server

## Deploy to VPS

\`\`\`bash
scp job-generator.html user@server:/var/www/html/job-generator.html
\`\`\`

## Features

- Parallel generation of resume and cover letter in a single request
- Automatic detection and parsing of the verification block (PASSED / FAILED + score %)
- Shimmer skeleton during loading
- Light and dark theme with localStorage persistence
- Cmd+Enter shortcut for quick generation
- Copy button — copies only the clean text without the verification block

## Author

[Sasha Arbatsky](https://xn--80aagffumg6aqm6m.xn--p1ai:8443) — UX/UI Designer
