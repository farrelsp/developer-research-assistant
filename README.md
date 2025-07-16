# 🧠 Developer Tools Research Assistant

**Developer Tools Research Assistant** is an AI-powered tool designed to help software developers research and discover technology stacks — such as frameworks, APIs, cloud platforms, databases, and more. It intelligently searches the web, extracts relevant tools, analyzes them, and presents structured comparisons to assist in technical decision-making.

---

## ✨ Features

- 🔍 **Query-Based Discovery**: Input a tool or technology name (e.g., `Firebase`), and the assistant will research and return a list of high-quality alternatives.
- 🧰 **Automatic Tool Extraction**: Extracts and identifies relevant tools from web search and article content.
- 📊 **Structured Analysis**: For each tool, you'll get:
  - Description
  - Pricing model
  - Open-source status
  - Supported programming languages
  - API availability
  - Integration capabilities
  - Underlying tech stack
- 🤖 **Powered by LLM & Web Crawling**: Combines the reasoning power of GPT-4o-mini with live web crawling and scraping via Firecrawl.
- 🧱 **Composable Workflow Engine**: Built using LangGraph to support multi-step research pipelines and easy feature extension.

---

## 🏗 Architecture Overview

```
User Query → Extract Tools → Research Tools → Analyze Tools → Recommendations
                   |                |               |               |
               Firecrawl        Firecrawl     LLM Analysis     LLM Summary
```

### Key Components:

- `Workflow`: Orchestrates the end-to-end research flow using LangGraph.
- `FirecrawlService`: Searches and scrapes online content.
- `DeveloperToolsPrompts`: Houses all system and user prompt templates.
- `models.py`: Defines structured data types like `ResearchState`, `CompanyInfo`, and `CompanyAnalysis`.

## 📦 Output Format

Each tool in the result includes:

```json
{
  "name": "Supabase",
  "description": "An open-source Firebase alternative...",
  "pricing_model": "Free tier with paid plans",
  "is_open_source": true,
  "api_available": true,
  "language_support": ["JavaScript", "Python", "Rust"],
  "tech_stack": ["PostgreSQL", "Realtime"],
  "integration_capabilities": ["Next.js", "Flutter"],
  "website": "https://supabase.io"
}
```
