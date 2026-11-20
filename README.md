# To-Do App: Creative Uses for Everyday Objects

A beginner-friendly Google Colab notebook that asks for an everyday object and uses the OpenAI Responses API to suggest one unusual, practical use.

## Repository structure

- to-do app.ipynb — the runnable Colab notebook.
- README.md — project overview and setup instructions.
- prompt.md — project requirements and technical specifications.

## Open and run in Google Colab

1. Clone this repository, or open its GitHub page.
2. In Google Colab, choose File → Open notebook → GitHub and paste the repository URL, or use this direct link after publishing: https://colab.research.google.com/github/Shiral47/chatbot-homework-4/blob/main/to-do%20app.ipynb.
3. Run the notebook cells from top to bottom.
4. When prompted, enter your OpenAI API key privately, then enter an everyday object.

An OpenAI API key is required at runtime. The notebook uses getpass to hide the key while entering it. Keep the key out of notebook source, saved outputs, commits, and GitHub repositories. If a key is ever exposed, revoke it and create a replacement.

The notebook uses the gpt-6-luna model through client.responses.create; API access and model availability depend on your OpenAI account.
