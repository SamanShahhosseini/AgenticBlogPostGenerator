# Agentic Blog Post Generator  

> **An end-to-end agentic AI system that generates SEO-friendly blog posts in English, Farsi, or Spanish — powered by LangGraph, Groq LLMs, and FastAPI.**  

---

## Overview  

The **Agentic Blog Post Generator** is a production-ready application that uses **agentic AI workflows** to automatically create **SEO-optimized blog posts**.  

It demonstrates my ability to:  
- Build **end-to-end AI systems** with **LangGraph orchestration**.  
- Use **Groq LLMs** for high-performance natural language generation.  
- Design **REST APIs** with **FastAPI**.  
- Deliver **real-world applications** (SEO + multilingual content).  

This project is part of my **portfolio showcase**, proving I can design AI systems that are **both technically advanced and practical for business use cases**.  

---

## Features  

The system supports **two modes of operation**:  

### 1 Only Topic Mode  
- Input: A **topic** (e.g., “Artificial Intelligence in Healthcare”).  
- Output:  
  - A **creative, SEO-friendly blog title**.  
  - A **detailed, SEO-optimized blog post** body.  

### 2 Topic + Language Mode  
- Input: A **topic** + **target language** (`Farsi` or `Spanish`).  
- Output:  
  - A **translated, SEO-friendly blog title**.  
  - A **detailed blog post body** in the selected language.  

Both modes ensure that the generated content is **SEO-ready**, using appropriate structure, keywords, and formatting.  

---

## Architecture  

- **FastAPI** → Provides a clean REST API at `/blogs`.  
- **LangGraph** → Manages workflows via nodes and state graphs.  
- **Groq LLMs** → Generates blog titles, content, and translations.  
- **Nodes** →  
  - `title_creation` → SEO-friendly blog title.  
  - `content_generation` → Detailed blog content.  
  - `translation` → Farsi/Spanish translation while keeping SEO context.  
- **State Management** → TypedDict (`BlogState`) tracks topic, content, and language.  

This modular design makes the system **easy to extend** with new languages or tools.  

---

## Installation & Setup  

### 1. Clone the repository  
```bash
git clone https://github.com/<your-username>/AgenticBlogPostGenerator.git
cd AgenticBlogPostGenerator
```

### 2. Create & activate a virtual environment  
```bash
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
```

### 3. Install dependencies  
```bash
pip install -r requirements.txt
```

### 4. Set environment variables  
Create a `.env` file in the root:  
```env
GROQ_API_KEY=your_groq_api_key
LANGCHAIN_API_KEY=your_langsmith_key   # optional for LangSmith integration
```

### 5. Run the API  
```bash
uvicorn app:app --reload
```

The API will be available at: [http://localhost:8000/blogs](http://localhost:8000/blogs)  

---

## Example Usage  

### Example Request (Topic Only)  
```bash
curl -X POST http://localhost:8000/blogs   -H "Content-Type: application/json"   -d '{
        "topic": "Artificial Intelligence in Finance"
      }'
```

### Example Response  
```json
{
  "data": {
    "topic": "Artificial Intelligence in Finance",
    "blog": {
      "title": "Transforming Finance: How AI is Revolutionizing Banking",
      "content": "Artificial Intelligence (AI) is transforming financial services..."
    }
  }
}
```

---

### Example Request (Topic + Language)  
```bash
curl -X POST http://localhost:8000/blogs   -H "Content-Type: application/json"   -d '{
        "topic": "Renewable Energy Trends",
        "language": "farsi"
      }'
```

### Example Response  
```json
{
  "data": {
    "topic": "Renewable Energy Trends",
    "blog": {
      "title": "روندهای نوین انرژی‌های تجدیدپذیر",
      "content": "انرژی‌های تجدیدپذیر به سرعت در حال تبدیل شدن به..."
    },
    "current_language": "farsi"
  }
}
```

---

## Roadmap  

- [ ] Add support for **more languages** (French, German, Arabic).  
- [ ] Improve SEO optimization with **embedding-based keyword expansion**.  
- [ ] Deploy API on **cloud (AWS/GCP)** with Docker.  
- [ ] Add **frontend UI** for non-technical users.  

---

## Why This Project is Relevant to Recruiters  

- Shows ability to build **real-world AI applications** (SEO + multilingual content).  
- Demonstrates strong skills in **LangGraph, FastAPI, and LLM orchestration**.  
- Proves experience with **production-grade architecture** (state management, modular design, environment configs).  
- Highlights capability to **bridge AI + business use cases** (content marketing, SEO, multilingual communication).  

---

## License  
MIT License.  
