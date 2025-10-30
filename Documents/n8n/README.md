n8n RAG News Summarizer

This project is an automated news summarization workflow built with n8n.
It fetches the latest headlines, selects the most relevant articles using embeddings (RAG), and generates a concise summary with OpenAI.

How it Works
- HTTP Request (NewsAPI) → Fetches top headlines
- Code (Prepare Articles) → Cleans and structures article text
- HTTP Request (OpenAI Embeddings) → Creates vectors for each article
- Code (Store Vectors) → Stores vectors for this run
- HTTP Request (OpenAI Embeddings) → Embeds the summary query
- Code (Similarity Search & Retrieve) → Picks top‑K relevant articles and builds context
- HTTP Request (OpenAI Chat) → Produces a 3‑paragraph summary
- Code (Format Output) → Outputs summary, sources, and metadata (tokens/cost)

Setup
1. Import `news.json` into your n8n instance.
2. Add your NewsAPI credential in n8n (for `top-headlines`).
3. Add your OpenAI API credential in n8n.
4. Execute the workflow (or add a Cron trigger if you want it scheduled).

Notes
- API keys and credentials are not included in the exported workflow (for security).
- You need to set up your own credentials in n8n to make it work.
- Outputs include a summary, selected sources, and simple token/cost metadata for transparency.


