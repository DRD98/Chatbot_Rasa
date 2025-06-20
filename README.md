# CHATBOT USING RASA

Rasa is an open-source framework for building conversational AI (chatbots and voice assistants). It uses:

- NLU (Natural Language Understanding) — to understand what users are saying.
- Core — to manage dialogue flow, using machine learning or rules.
- Action Server — for running custom logic (API calls, databases, etc.).

This ChatBot retrieves the weather information for some cities.

### Important Keywords

- `intent`: What the user wants the bot to do
- `action`: What the bot does (eg: respond, API calls)
- `entities`: Important data in the message that the user sent.
- `slots`: Stores entity values; Memory of data

### Important project files

- `data/stories.yml`: Contains a form of training data which are sample conversations between a user and a bot in the form of intents.
- `data/nlu.yml`: This is the training data for the NLU model that defines the intends (what the user could ask the bot to do).
- `action.py`: This file is used to create custom actions, like API calls or calling an external servers.
- `domain.yml`: It contains the list of intents with the bot's responses and actions it can perform.
- `config.yml`: Defines the configuration of the NLU and the core model. If any other model is used (except the NLU model), the pipeline has to be defined here.

### Commands

- `rasa init`: Initialize a new Rasa project
- `rasa train`: Train the model (NLU + Core)
- `rasa shell`: Chat with the bot in terminal
- `rasa shell nlu`: Test only NLU parsing
- `rasa run --enable-api`: Start Rasa server with REST API. The entire HTTP API will be enabled.
- `rasa run actions`: Start action server (for custom actions). If there are custom actions, this command has to be executed first in a seperate terminal first, before running any other commands.
- `rasa data validate`: Validate training data
- `rasa visualize`: Shows a graph of conversation flows using the training data from `data/stories.yml`.
