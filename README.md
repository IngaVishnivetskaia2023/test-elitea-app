# Quiz CLI

An interactive command-line quiz game for learning JavaScript. This small, educational project demonstrates modern Node.js features such as ES modules, async/await, file system operations, user input handling, and basic object-oriented design.

## Project description

Quiz CLI is a terminal-based quiz application that lets you select a category, choose how many questions to answer, and then play through the quiz interactively. It's designed to be small and easy to read, making it a good example project for learning core JavaScript and Node.js concepts.

The repository includes:
- index.js: Entry point and main application loop
- src/: Helper modules (colors, input, quiz logic)
- data/questions.json: Sample question data

## Prerequisites

- Node.js v18.0.0 or newer (the project uses ES modules and the fs/promises API)
- npm (optional, for running scripts)

Verify your Node version with:

node --version

## Setup instructions

1. Clone the repository:

   git clone <repository-url>
   cd <repository-directory>

2. Install dependencies

   This project has no external runtime dependencies. If you want to run tests (when present) or add dev dependencies, use npm:

   npm install

3. Inspect or add questions

   Questions are stored in data/questions.json. You can add new categories or questions there using the provided JSON structure. Each question object supports:
   - question: string
   - options: array of strings
   - answer: index (0-based) of the correct option
   - explanation: optional string explaining the answer

## How to run the project

Start the CLI with:

npm start

Or run directly with node:

node index.js

The application will:
- Show a welcome banner
- Prompt you to choose a category
- Prompt you to choose how many questions to answer
- Ask questions one-by-one and show results at the end

## Key features

- Interactive terminal quiz experience
- Category-based question selection
- Option to choose question count (All / 3 / 5 when available)
- Simple, dependency-free color helper using ANSI escape codes
- Clear, modular code organized into small ES module files
- Demonstrates common JavaScript/Node.js techniques:
  - ES modules (import/export)
  - Async/await and Promises
  - File system operations (fs/promises)
  - Readline-based user input
  - Classes and object-oriented design
  - Array methods, destructuring, template literals, and error handling

## Extending the quiz

- Add new categories and questions in data/questions.json
- Extend src/quiz.js to support shuffling, scoring, time limits, or scoring breakdowns
- Add unit tests and continuous integration as needed

## Troubleshooting

- If you see an error about ES modules or import syntax, ensure package.json contains "type": "module" (it does in this project) and you are running Node v18+.
- If the CLI seems unresponsive, press Ctrl+C to exit and try running node index.js directly.

## License

This project is licensed under the MIT License.

---

Happy quizzing! 🎉
