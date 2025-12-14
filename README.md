
# LangGraph.js-MongoDB-Example

This repository demonstrates how to use LangGraph with MongoDB for building and managing AI agents and conversational applications using an agentic approach. It showcases the integration of language models, graph-based conversation management, and MongoDB for data persistence, enabling the creation of intelligent, autonomous agents in TypeScript and Express.js.

## Features

- Utilizes LangGraph for managing agentic conversational flows in TypeScript
- Integrates with MongoDB Atlas for storing and retrieving conversation data
- Implements a RESTful API using Express.js for chat interactions
- Uses OpenAI's GPT model and Anthropic's API for generating responses
- Includes a tool for employee lookup using MongoDB Atlas vector search


## Written tutorial → https://mdb.link/article-qXDrWKVSx1w
Reference : https://www.mongodb.com/docs/atlas/ai-integrations/langgraph-js/build-agents/?utm_campaign=devrel&utm_source=youtube&utm_medium=organic_social&utm_content=qXDrWKVSx1w&utm_term=jesse.hall

## Prerequisites

- [Node.js and npm](https://nodejs.org/)
- [MongoDB Atlas account](https://www.mongodb.com/cloud/atlas)
- [OpenAI API key](https://platform.openai.com/account/api-keys)
- [Anthropic API key](https://www.anthropic.com/claude)

## Installation

1. Clone this repository:

```bash
git clone https://github.com/mongodb-developer/LangGraph-MongoDB-Example.git 
cd LangGraph-MongoDB-Example
```

2. Install the required dependencies:

```bash
npm install
```

3. Set up your environment variables:
- Create a `.env` file in the root directory
- Add your API keys and MongoDB URI:
  
  ```
  OPENAI_API_KEY=your_openai_api_key_here
  ANTHROPIC_API_KEY=your_anthropic_api_key_here
  MONGODB_ATLAS_URI=your_mongodb_atlas_uri_here
  ```

## Seed the Database

1. Run the seed script to generate and seed the database:

```bash
npm run seed
```

## Usage

1. Start the server:

```bash
npm run dev
```

2. Use the following API endpoints:

- Start a new conversation:
  ```
  curl -X POST -H "Content-Type: application/json" -d '{"message": "Your message here"}' http://localhost:3000/chat
  ```
- Continue an existing conversation:
  ```
  curl -X POST -H "Content-Type: application/json" -d '{"message": "Your follow-up message"}' http://localhost:3000/chat/{threadId}
  ```

## Project Structure

- `index.ts`: Entry point of the application, sets up the Express server and API routes
- `agent.ts`: Defines the LangGraph agent, tools, and conversation flow
- `seed-database.ts`: Script for generating and seeding synthetic employee data into MongoDB

## How it works

1. The seed script in `seed-database.ts` generates synthetic employee data and populates the MongoDB database.
2. The LangGraph agent is defined in `agent.ts`, including the conversation graph structure and tools.
3. MongoDB operations are integrated directly into the agent for storing and retrieving conversation data.
4. The Express server in `index.ts` provides API endpoints for starting and continuing conversations.
5. User inputs are processed through the LangGraph agent, generating appropriate responses and updating the conversation state.
6. Conversation data is persisted in MongoDB Atlas, allowing for continuity across sessions.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.




Some Example :

npx ts-node seed-database.ts

This command runs your TypeScript file directly without manually compiling it to JavaScript first. 
npx: This tool (included with npm v5.2.0 and later) runs a Node.js package executable from the local node_modules/.bin directory or a central cache, avoiding the need to install the package globally.

ts-node: This is a TypeScript execution engine for Node.js. It performs just-in-time (JIT) transpilation, transforming your TypeScript (.ts file) into executable JavaScript in memory, and then runs that JavaScript using the Node.js environment.

Functionality: It allows you to use TypeScript features (like type annotations) during development, often with built-in type checking by default, simplifying the development workflow by removing the manual compile step. 
