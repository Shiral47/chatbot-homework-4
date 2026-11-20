# Project Requirements and Technical Specifications

## Repository rules

- Keep all code deliverables in Google Colab notebooks (`.ipynb`).
- Commit new code changes and push them to the configured GitHub `origin` remote.
- Never put passwords, API keys, or database connection strings in source files, outputs, commits, or GitHub.

## Club chatbot notebook

- Maintain `club-chatbot.ipynb` as the project's Google Colab notebook.
- Install LangGraph, LangChain, the OpenAI integration, the PostgreSQL checkpoint saver, Psycopg with binary support, and Gradio.
- Load `OPENAI_API_KEY` and `SUPABASE_DB_URL` from `google.colab.userdata`.
- Use the model name `openai:gpt-6-luna` through `init_chat_model`.
- Support the clubs Astronomy, Cooking, Football, World Geography, and Python Programming, with Astronomy as the default.
- Persist each thread's messages and active topic in Supabase PostgreSQL with a LangGraph `PostgresSaver` checkpointer.
- Provide a Gradio Blocks interface for topic selection, saved conversations, new conversations, chat history, and message submission.
- Keep the per-call SystemMessage out of persisted conversation history.

## Strict topic boundaries

- Classify the overall intent and real-world context before answering. Do not decide from isolated keywords such as “food,” “eat,” or “recipe.”
- Answer only when the primary intent clearly belongs to the active club. Refuse off-topic, previous-topic, mixed, or hybrid requests whose main purpose touches another club's domain.
- Never bridge two topics or answer an in-scope portion of a hybrid request. On refusal, name the active club and suggest switching to the relevant club using the topic selector.
- In the Cooking club, refuse requests about sports training, match preparation, athletics, sports coaching, athletic performance, game-day nutrition, or what players should eat before, during, or after a game. These belong to Football even if the request mentions food, meals, eating, or recipes.
- For example, refuse “As a football coach, what should my players eat before a game?” in Cooking without offering food, nutrition, or cooking advice. State that the active club is Cooking and suggest switching to Football.
- Build the dynamic system prompt in `build_system_message(topic)` and preserve all other graph, persistence, and interface behavior when changing the prompt.
