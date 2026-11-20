# Club Chatbot

A Google Colab notebook for a persistent, topic-scoped club chatbot. It uses LangGraph and OpenAI for responses, Supabase PostgreSQL for checkpoint persistence, and Gradio for the interface.

## Repository structure

- `club-chatbot.ipynb` — the complete Google Colab notebook.
- `README.md` — setup and usage instructions.
- `prompt.md` — project requirements and technical specifications.
- `agent.md` — repository instructions for future code changes.

## Open and run in Google Colab

1. Open the notebook from GitHub in Colab: [Open club-chatbot.ipynb](https://colab.research.google.com/github/Shiral47/chatbot-homework-4/blob/main/club-chatbot.ipynb).
2. Run the dependency installation cell. It installs Gradio 5.50.0 for a consistent UI version.
3. After installation completes, choose **Runtime → Restart session**, then continue with the next section, **Load secrets and initialize the chat model**.
4. Add these two values in Colab's **Secrets** panel and enable notebook access:
   - `OPENAI_API_KEY` — your OpenAI API key.
   - `SUPABASE_DB_URL` — the PostgreSQL connection string from your Supabase project.
5. For Colab's IPv4-only network, use the exact **Session pooler** URL from **Supabase Dashboard → Connect → Session pooler** (port 5432). Do not use a direct `db.*.supabase.co` URL if it resolves to IPv6.
6. Run the remaining cells in order. The notebook includes a persistence test cell and starts the Gradio app with a share link.

Keep both credentials in Colab Secrets; never paste them into notebook code, outputs, commits, or GitHub. Anyone who has the Gradio share link can use the running app, its OpenAI API quota, and its Supabase-backed conversations, so share the link only with trusted people.
