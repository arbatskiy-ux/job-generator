# Генератор откликов

AI-инструмент для автоматической адаптации резюме и написания сопроводительных писем под конкретную вакансию. Один HTML-файл без зависимостей — открывается в браузере и работает.

![Material Design 3](https://img.shields.io/badge/Material_Design-3-6750A4?style=flat-square)
![Vanilla HTML](https://img.shields.io/badge/Vanilla-HTML%2FCSS%2FJS-E34F26?style=flat-square)
![Notion API](https://img.shields.io/badge/Notion-API-000000?style=flat-square&logo=notion)
![Claude AI](https://img.shields.io/badge/Claude-AI-CC785C?style=flat-square)

[English version](README.md)

## Как работает

1. Вставляешь текст вакансии
2. Нажимаешь **Сгенерировать**
3. Claude адаптирует резюме под требования вакансии и пишет сопроводительное письмо
4. Каждый результат автоматически проверяется на галлюцинации с оценкой в процентах

Промпты хранятся в Notion и подтягиваются при каждой генерации — обновляешь промпт в Notion, инструмент подхватывает без правки кода.

## Стек

- **Vanilla HTML/CSS/JS** — один файл, без фреймворков и сборщиков
- **Material Design 3** — токены, elevation через surface tint, Extended FAB, shimmer-скелетон
- **Claude API** (claude-sonnet-4) — параллельная генерация резюме и письма
- **Notion API** — хранение системных промптов, подтягиваются при каждом запросе

## Настройка

\`\`\`js
const CLAUDE_KEY = 'sk-ant-...';
const NOTION_KEY = 'secret_...';
const NOTION_RESUME_ID = '...';
const NOTION_LETTER_ID = '...';
\`\`\`

## Возможности

- Параллельная генерация резюме и письма за один запрос
- Автоматический парсинг блока проверки (PASSED / FAILED + оценка %)
- Shimmer-скелетон во время загрузки
- Светлая и тёмная тема с сохранением в localStorage
- Cmd+Enter для быстрой генерации
- Кнопка копирования — копирует только чистый текст

## Автор

[Саша Арбатский](https://xn--80aagffumg6aqm6m.xn--p1ai:8443) — UX/UI дизайнер
