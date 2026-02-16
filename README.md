# Quiz CLI

An interactive command-line quiz game to help you learn and practice JavaScript fundamentals. This lightweight project demonstrates modern Node.js features (ES modules), async/await, file I/O, user input handling, simple OOP, and helpful array/string utilities — all with zero external dependencies.

---

## Project description

Quiz CLI is a small educational command-line application that presents multiple-choice questions grouped by category. It's designed as a learning example for developers who want to see how to build a friendly CLI app using native Node.js APIs and common JavaScript patterns.

Key goals:
- Provide an enjoyable command-line quiz experience
- Demonstrate ES modules, Promises/async-await, and file system usage
- Showcase a clean separation between input handling, UI helpers (colors), and quiz logic

---

## Prerequisites

- Node.js 18.x or newer (the project uses ES modules and the built-in fs/promises API)
- A POSIX-compatible terminal (colors and formatting work best in modern terminals)

---

## Setup instructions

1. Clone the repository:

   git clone <repository-url>
   cd test-elitea-app

2. (Optional) Install dependencies. This project has no runtime dependencies, but if you later add any, run:

   npm install

3. Confirm Node.js version:

   node -v

It should be >= 18.0.0 as specified in the package.json engines field.

---

## How to run the project

Start the quiz from the project root:

npm start

Or run directly with node:

node index.js

Available scripts (package.json):
- start: Runs the CLI (node index.js)
- test: Runs Node's built-in test runner (node --test)

---

## Usage overview

- When launched, you'll see a welcome banner and a prompt to choose a category.
- Choose how many questions to answer (All / 3 / 5 depending on availability).
- Answer questions by selecting the number corresponding to the option.
- After each question you'll be able to continue, and at the end you'll see your score and explanations.
- You will be prompted to play again.

---

## Project structure

```
test-elitea-app/
├── index.js            # Main entry point and app loop
├── package.json        # Project metadata and scripts
├── data/
│   └── questions.json  # Quiz content and categories
└── src/
    ├── colors.js       # Terminal color helpers (ANSI codes)
    ├── input.js        # Readline-based input helpers
    └── quiz.js         # Quiz game logic and question flow
```

---

## Key features

- Minimal, dependency-free implementation
- Uses ES modules (import / export)
- Async/await and Promises for file I/O and user prompts
- Readable code showing OOP (Quiz class) and array utilities (shuffle, map, filter)
- ANSI color helpers for a nicer terminal UX
- Data-driven questions (data/questions.json) so it's easy to add categories or questions

---

## Extending the quiz

- Add new categories or questions in data/questions.json following the same structure.
- Enhance input.js to support richer input patterns or validation.
- Improve scoring, timing, or add difficulty levels.
- Add unit tests around the Quiz class and input helpers.

---

## Troubleshooting

- If the app fails to run, ensure Node.js v18+ is installed.
- If colors or banner formatting look odd, try a different terminal emulator or disable ANSI colors.
- If you add dependencies, run npm install and re-run npm start.

---

## License

MIT
