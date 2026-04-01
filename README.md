# NLP Chatbot using Hugging Face Transformer

A conversational AI chatbot built with Microsoft's DialoGPT-medium model via the Hugging Face Transformers library. Runs on Google Colab or any Python environment.

## Features

- AI-powered responses using DialoGPT-medium
- Multi-turn conversation with chat history
- Built-in fixed responses for common topics (AI, Python, greetings)
- `help` command to list all available commands
- `reset` command to clear conversation history
- `history` command to view turn count
- Auto-reset of history after 10 turns to prevent token overflow
- Empty input validation
- Full error handling for runtime and generation errors

## Tech Stack

- Python 3.x
- [Hugging Face Transformers](https://huggingface.co/docs/transformers)
- [PyTorch](https://pytorch.org/)
- Model: [microsoft/DialoGPT-medium](https://huggingface.co/microsoft/DialoGPT-medium)

## Getting Started

### Run on Google Colab (Recommended)

1. Open [Google Colab](https://colab.research.google.com/)
2. Upload `NLP chatbot.ipynb`
3. Run all cells from top to bottom

### Run Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/Balajee12/NLP-chatbot-using-transformer.git
   cd NLP-chatbot-using-transformer
   ```

2. Install dependencies:
   ```bash
   pip install transformers torch
   ```

3. Open and run the notebook:
   ```bash
   jupyter notebook "NLP chatbot.ipynb"
   ```

## Usage

Once the model loads, type your message and press Enter:

```
Chatbot: Hello! I am your AI assistant. How can I help you today?
Type 'help' for available commands.

You: hello
Chatbot: Hello! Nice to meet you. How can I assist you today?

You: what is artificial intelligence
Chatbot: Artificial Intelligence refers to the simulation of human intelligence...

You: help
Chatbot: Available commands:
  'hello'              - Greeting
  'artificial intelligence' - Learn about AI
  'python'             - Learn about Python
  'reset'              - Clear conversation history
  'history'            - Show turn count
  'exit' / 'quit'      - End the chat
  Anything else        - AI-generated response

You: reset
Chatbot: Conversation history cleared. Let's start fresh!

You: exit
Chatbot: Goodbye! We had 3 exchanges.
```

## Commands

| Command | Description |
|---|---|
| `hello` | Greeting response |
| `artificial intelligence` | Fixed explanation of AI |
| `python` | Info about Python language |
| `help` | List all commands |
| `reset` | Clear conversation history |
| `history` | Show number of turns |
| `exit` / `quit` / `bye` | End the session |
| anything else | DialoGPT-generated response |

## Project Structure

```
NLP-chatbot-using-transformer/
├── NLP chatbot.ipynb   # Main notebook
└── README.md           # This file
```

## Notes

- First run downloads the DialoGPT-medium model (~863 MB)
- Conversation history auto-resets after 10 turns to avoid exceeding the model's token limit
- If the model generates an empty response, the chatbot prompts you to rephrase
