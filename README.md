# LLM Query System

This repository contains a distributed system that includes:
1. A Python program to run **Llama2** and **Mistral** models.
2. An API server using Express.js or Nest.js to interface with the Python program.

## Table of Contents
- [Python Program](#python-program)
  - [Features](#features)
  - [Conditions](#conditions)
- [Node.js API Server](#nodejs-api-server)
  - [Features](#features-1)
  - [Conditions](#conditions-1)
- [Setup](#setup)
  - [Docker](#docker)
  - [Running the Application](#running-the-application)

## Python Program

### Features
1. Allows the user to select a model (**Llama2** or **Mistral**) at the start.
2. Enables the user to send queries to the selected model and receive answers from the LLM.
3. Maintains communication context between the user and the LLM, allowing for continuous conversations similar to ChatGPT.

### Conditions
1. The program should be wrapped in a Docker container.

## Node.js API Server

### Features
1. Sends queries to the Python program.
    - Includes the selected model and the question in the request body.
2. Lists conversation history, ordered by date in descending order.
3. Provides details of a specific conversation.
    - Displays the list of questions and responses within a specific conversation.

### Conditions
1. The API server is wrapped in a Docker container.
2. The entire application is runnable using a single `docker-compose up --build` command.
3. Postgres db is used.
4. TypeScript is used for type safety.
5. Nest.js for the API server.

## Setup

### Docker
Ensure you have Docker and Docker Compose installed on your machine.

### Running the Application
1. Clone this repository:
    ```bash
    git clone https://github.com/semirhamid/llm-query-system.git
    cd llm-query-system
    ```
2. Build and start the application using Docker Compose:
    ```bash
    docker-compose up --build
    ```

### Project Structure
```
llm-query-system/
├── python/
│   ├── Dockerfile
│   ├── app.py
│   └── requirements.txt
├── nodejs/
│   ├── Dockerfile
│   ├── app.js (or app.ts for TypeScript)
│   ├── package.json
│   └── tsconfig.json (if using TypeScript)
├── docker-compose.yml
└── README.md
```



## Contributing
Contributions are welcome! Please open an issue or submit a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

