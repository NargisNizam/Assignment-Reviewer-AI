# Simple Assignment Reviewer

A terminal-only teaching project using LangChain, LangGraph, LangSmith, and Groq.
Use Python 3.11 or 3.12. There is one Python file and no web interface.

## Windows setup (Command Prompt)

Open a terminal inside the extracted assignment-reviewer folder:

```bat
py -3.11 -m venv .venv
.venv\Scripts\activate
python -m pip install -r requirements.txt
copy .env.example .env
```

Use -3.12 instead if that is your installed Python version.
Edit .env to add your Groq API key from https://console.groq.com/keys.

```bat
python app.py
```

Type your answer on one line and press Enter.

## macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
cp .env.example .env
# Edit .env to add your Groq key.
python app.py
```

## What each library does

- LangChain: combines the prompt and model, returning structured marks/feedback.
- LangGraph: evaluates the answer and routes scores 4–6 to teacher review.
- LangSmith: automatically traces the graph and model calls when enabled.

To enable LangSmith, get a key from https://smith.langchain.com/, set
LANGSMITH_API_KEY in .env, and change LANGSMITH_TRACING to true. Run the app
again. Open the assignment-review project in LangSmith to inspect the run.
Tracing records prompts and answers; use fictional student submissions.

## Sample answer

Supervised learning uses labeled data, such as emails labeled spam or not spam. Unsupervised learning finds patterns in unlabeled data, such as grouping customers by purchasing behavior.

## Scope

Scores are suggestions. Teacher review is an on-screen flag, with no saved
queue or approval flow. Model scores may vary. No API keys are included.
If your account cannot access the default model, set GROQ_MODEL to an available
Groq model supporting tool calling. API/network errors appear in the terminal.
Syntax and ZIP integrity checked; live API calls and dependency installation
were not tested in the packaging environment.
