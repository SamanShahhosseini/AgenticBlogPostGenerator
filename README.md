# Agentic Blog Post Generator

Agentic Blog Post Generator is an agentic application designed to automatically generate SEO-friendly blog posts based on user inputs. It leverages advanced language models and an agentic workflow to deliver high-quality content optimized for search engines. 

## Features

This project supports two main modes of operation:

1. **Only Topic:**  
   - The user provides a topic.
   - The system generates a creative, SEO-friendly blog post title and a detailed blog post body related to the topic.
   - Both the title and body are optimized for SEO.

2. **Topic and Language:**  
   - The user provides both a topic and a desired language.
   - The system generates a creative, SEO-friendly blog post title and body in the specified language.
   - The content is adapted to cultural and linguistic nuances of the target language, maintaining SEO best practices.

## How It Works

- The system is built on FastAPI for serving endpoints.
- Blog post generation is managed by an agentic workflow using `langgraph` and `langchain` libraries.
- For the "Only Topic" mode, the system:
  - Creates a blog title using language model prompts.
  - Generates detailed blog content with Markdown formatting.
- For the "Topic and Language" mode, the system:
  - Generates the title and content in the default language.
  - Translates the content to the specified language, ensuring style and cultural adaptation.
  - Currently supports conditional translation nodes for languages such as Farsi and Spanish.

## API Usage

### POST `/blogs`

**Request Body:**
- Only Topic:
  ```json
  { "topic": "Agentic AI" }
  ```
- Topic and Language:
  ```json
  { "topic": "Agentic AI", "language": "Farsi" }
  ```

**Response:**
- Returns a JSON object containing the SEO-friendly blog post title and content.

## Project Structure

- `app.py` – FastAPI application and main endpoint.
- `src/graphs/graph_builder.py` – Agentic workflow builder for blog generation.
- `src/nodes/blog_node.py` – Node logic for blog title, content, and translation.
- `src/states/blogstate.py` – State definitions for blog generation.
- `requirements.txt` / `pyproject.toml` – Project dependencies.

## Setup

1. **Clone the repository**  
   ```bash
   git clone https://github.com/SamanShahhosseini/AgenticBlogPostGenerator.git
   cd AgenticBlogPostGenerator
   ```
2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```
3. **Set up environment variables**  
   - Copy `.env.example` to `.env` and configure your API keys as needed.

4. **Run the application**  
   ```bash
   uvicorn app:app --reload
   ```
   The API will be available at `http://localhost:8000/blogs`.

## Dependencies

- Python 3.11+
- FastAPI
- Uvicorn
- LangChain, LangGraph, LangChain Groq, LangChain Core, LangChain Community

## License

This project is licensed under the MIT License.

---

> **Note:**  
> The search results provided above may be incomplete due to result limitations.  
> For a full view of the repository content, visit [AgenticBlogPostGenerator on GitHub](https://github.com/SamanShahhosseini/AgenticBlogPostGenerator).
