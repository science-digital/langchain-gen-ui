# Generative UI with LangChain.js 🦜🔗

![Generative UI with LangChain.js](./public/gen_ui_diagram.png)

## Overview

This application aims to provide a template for building generative UI applications with LangChain.js.
It comes pre-built with a few UI features which you can use to play about with gen ui. The UI components are built using [Shadcn](https://ui.shadcn.com/).

## Architecture

Some notes on the application architecture / project structure: [ARCHITECTURE.md](./ARCHITECTURE.md)

## Useful links
- https://js.langchain.com/v0.2/docs/how_to/generative_ui
- https://langchain-ai.github.io/langgraphjs/
- https://api.python.langchain.com/en/latest/community_api_reference.html

## Getting Started

### Installation

First, clone the repository and install dependencies:

```bash
git clone https://github.com/bracesproul/gen-ui.git

cd gen-ui

yarn install
```

Next, if you plan on using the existing pre-built UI components, you'll need to set a few environment variables:

Copy the [`.env.example`](./.env.example) file to `.env`:

The `OPENAI_API_KEY` is required. LangSmith keys are optional, but highly recommended if you plan on developing this application further.

Get your OpenAI API key from the [OpenAI dashboard](https://platform.openai.com/login?launch).

[Sign up/in to LangSmith](https://smith.langchain.com/) and get your API key.

Create a new [GitHub PAT (Personal Access Token)](https://github.com/settings/tokens/new) with the `repo` scope.

[Create a free Geocode account](https://geocode.xyz/api).

```bash
# ------------------LangSmith tracing------------------
LANGCHAIN_API_KEY=...
LANGCHAIN_CALLBACKS_BACKGROUND=true
LANGCHAIN_TRACING_V2=true
# -----------------------------------------------------

GITHUB_TOKEN=...
OPENAI_API_KEY=...
GEOCODE_API_KEY=...
FIRECRAWL_API_KEY=...
```

### Running the Application

To run the application in development mode run:

```bash
yarn dev
```

This will start the application on [`http://localhost:3000`](http://localhost:3000).

To run in production mode:

```bash
yarn start

yarn build
```

#### Deployment

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fbracesproul%2Fgen-ui&env=GITHUB_TOKEN,OPENAI_API_KEY,GEOCODE_API_KEY,FIRECRAWL_API_KEY,LANGCHAIN_API_KEY,LANGCHAIN_CALLBACKS_BACKGROUND,LANGCHAIN_TRACING_V2&project-name=gen-ui&repository-name=gen-ui)

### Go further

If you're interested in ways to take this demo application further, I'd consider the following:

- Generating entire React components to be rendered, instead of relying on pre-built components. OR: Using the LLM to build custom components using a UI library like [Shadcn](https://ui.shadcn.com/).
- Multi-tool and component usage. Update the LangGraph agent to call multiple tools, and appending multiple different UI components to the client rendered UI.
- Generative UI outside of the chatbot window. Have the UI dynamically render in different areas on the screen. E.g a dashboard, where the components are dynamically rendered based on the LLMs output.
