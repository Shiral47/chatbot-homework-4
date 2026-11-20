# Project Requirements and Technical Specifications

- Create a beginner-friendly Google Colab notebook named to-do app.ipynb.
- Include a quiet SDK installation step (%pip -q install openai).
- Request the OpenAI API key securely at runtime with getpass; never hardcode, display, save, commit, or upload the key.
- Prompt for an everyday object using Python input().
- Call the OpenAI Responses API with client.responses.create and model gpt-6-luna to request exactly one unusual, creative, practical use.
- Organize the notebook into clean cells with Markdown explanations and beginner-friendly comments.
- Add a README describing the project and repository structure, explaining how to clone/open/run the notebook in Google Colab from GitHub, and emphasizing API-key security.
- Initialize Git on main, set the project commit identity to Shir Alkalay / shiralklay2000@gmail.com, create a public GitHub repository under Shiral47, set origin, and push with upstream tracking after browser authentication.
- Record the setup and project work in Git commits; never place passwords or tokens in project files.

## Club Chatbot Topic-Boundary Requirements

The `club-chatbot.ipynb` notebook must enforce strict topic boundaries for these clubs: Astronomy, Cooking, Football, World Geography, and Python Programming.

- Before answering, classify the overall intent and real-world context of the latest question. Do not classify from isolated keywords such as “food,” “eat,” or “recipe.”
- Answer only when the primary intent clearly belongs to the active club. Refuse off-topic, previous-topic, mixed, or hybrid requests when their main purpose involves another club's domain.
- Never bridge two topics or answer the in-scope part of a hybrid request. On refusal, explicitly name the active club and suggest switching to the relevant club with the topic selector.
- In the Cooking club, sports training, match preparation, athletics, sports coaching, athletic performance, game-day nutrition, and questions about what players should eat before, during, or after a game belong to Football and must be refused, even if the request also mentions food, meals, eating, or recipes.
- For example, in Cooking, refuse “As a football coach, what should my players eat before a game?” without offering meal, nutrition, or cooking advice; state that the user is in the Cooking club and suggest switching to Football.
- Build the `SystemMessage` dynamically from the current topic in `build_system_message(topic)`. Send it to the model for each call without adding it to persisted conversation history.
