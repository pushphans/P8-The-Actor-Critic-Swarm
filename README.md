# P8-The-Actor-Critic-Swarm

An AI-powered documentation generation workflow that uses an actor-critic pattern to produce high-quality technical documentation. The project combines LangGraph with an LLM-based writer and reviewer loop so that draft documentation is iteratively refined until it reaches a production-grade standard.

## Overview

P8-The-Actor-Critic-Swarm is a prototype of an agentic documentation system built with Python, LangChain, and LangGraph. It simulates a review workflow in which:

- an Actor node generates a technical documentation draft,
- a Critic node reviews the draft against quality criteria,
- and the workflow loops until the documentation is approved or the retry limit is reached.

This makes the project useful for learning how to build self-improving AI agents for writing, reviewing, and refining structured outputs.

## Key Features

- Actor-critic workflow for iterative content refinement
- Technical documentation generation in Markdown
- Strict review criteria for completeness and clarity
- LangGraph-based stateful orchestration
- Modular design for extending the workflow

## Tech Stack

- Python
- LangChain
- LangGraph
- OpenAI GPT-4o-mini
- Pydantic
- FastAPI
- Pydantic Settings

## Project Structure

```text
.
├── app/
│   ├── agent/
│   │   └── graph.py
│   ├── core/
│   │   └── config.py
│   └── main.py
├── main.py
├── pyproject.toml
├── requirements.txt
└── README.md
```

## Prerequisites

Before running the project, make sure you have:

- Python 3.12 or higher
- pip or uv installed
- An OpenAI API key

## Installation

1. Clone the repository

```bash
git clone https://github.com/pushphans/P8-The-Actor-Critic-Swarm.git
cd P8-The-Actor-Critic-Swarm
```

2. Create and activate a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

3. Install dependencies

```bash
pip install -r requirements.txt
```

4. Configure environment variables

Create a `.env` file or export your API key:

```bash
export OPENAI_API_KEY=your_openai_api_key
```

## How It Works

The workflow inside `app/agent/graph.py` follows this pattern:

1. Actor node
   - Writes a draft of technical documentation based on the user request.

2. Critic node
   - Reviews the draft for formatting, completeness, clarity, and error handling.

3. Routing logic
   - If the review fails, the workflow sends the draft back to the Actor for revision.
   - If the documentation passes, it moves to the finalization step.

## Example Usage

The repository includes an example workflow run that starts with a user prompt such as:

```text
I have created a database querying agent for a business app for a foreign client
```

The agent then generates and reviews a documentation draft until it meets the expected quality bar.

## Notes

This project is a practical example of an iterative AI writing workflow. It is well suited for learning how to:

- build stateful LangGraph agents,
- implement review loops with LLMs,
- and refine generated outputs through structured feedback.

## Contributing

Contributions, improvements, and new workflow examples are welcome. Feel free to open an issue or submit a pull request.
