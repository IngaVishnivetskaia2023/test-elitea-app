# Quiz CLI

An interactive command-line quiz game for learning JavaScript and related topics. This small Node.js application demonstrates ES Modules, async/await, file system operations, user input handling, simple OOP with classes, and useful array & string utilities — all with no external dependencies.

---

## Table of Contents

- Project description
- Key features
- Repository structure
- Requirements
- Setup
- How to run
- How to add or edit questions
- Development notes
- License

---

## Project description

Quiz CLI is a terminal-based quiz application that lets you choose a category and answer multiple-choice questions. It supports selecting the number of questions, shows progress, displays results and a review of incorrect answers, and provides colored output for a nicer UX.

The application is implemented with readable, modular ES modules and example code intended to be educational as well as functional.

---

## Key features

- Multiple categories (JavaScript, Node.js, General Programming)
- Choose how many questions to attempt (All / 3 / 5)
- Randomized question order (Fisher–Yates shuffle)
- Visual progress bar and per-question feedback
- Final score, performance message and incorrect-answer review
- Plain Node.js implementation (no external packages)
- Clear, modular source: input handling, quiz logic, and terminal color helpers

---

## Repository structure

- index.js — Main entry point and application loop
- package.json — Project metadata and npm scripts
- data/
  - questions.json — Categories and question banks (text, options, correct index, explanation)
- src/
  - input.js — Readline-based prompt, select, confirm, pressEnter helpers
  - quiz.js — Quiz class: shuffling, asking questions, scoring, results
  - colors.js — Small ANSI color helper functions for styled terminal output
- .DS_Store — macOS folder metadata (can be ignored)

Example data layout (data/questions.json):
- categories
  - javascript (JavaScript Basics)
  - nodejs (Node.js Fundamentals)
  - general (General Programming)
Each category contains an array of question objects with fields: question, options, answer (index), explanation.

---

## Requirements

- Node.js 18.0.0 or higher

This project uses ES Modules (type: "module" in package.json).

---

## Setup

1. Clone the repository:
   git clone https://github.com/IngaVishnivetskaia2023/test-elitea-app.git

2. Change into the project directory:
   cd test-elitea-app

3. (Optional) Install dependencies:
   There are no runtime dependencies defined in package.json. If you add packages, run:
   npm install

---

## How to run

Start the quiz from the project root:

- Using npm script:
  npm start

- Or directly with node:
  node index.js

Follow the interactive prompts to:
- Choose a category
- Select number of questions to attempt
- Answer each question by entering the option number
- Press Enter between questions when prompted
- View results and choose whether to play again

To run the project's tests (if/when tests are added), the package.json defines:
  npm test
which currently runs `node --test`.

---

## How to add or edit questions

Edit data/questions.json. Each category contains a "questions" array. Each question object has:
- question: string
- options: array of strings
- answer: integer (0-based index into options)
- explanation: (optional) string shown after answering

Example:
{
  "question": "What keyword is used to declare a constant in JavaScript?",
  "options": ["var", "let", "const", "define"],
  "answer": 2,
  "explanation": "The 'const' keyword declares a block-scoped constant..."
}

After editing, run the app to see the updated question set.

---

## Development notes

- The quiz order is randomized on each play using the shuffle function (Fisher–Yates).
- Terminal coloring is implemented via ANSI escape codes in src/colors.js — easy to extend.
- Input helpers in src/input.js use Node's readline and return Promises for simple async/await usage.
- The Quiz class (src/quiz.js) handles question flow, scoring, progress rendering, and results display.

If you plan to extend the app:
- Add new categories or questions to data/questions.json.
- Add unit tests and update the "test" script in package.json.
- Consider adding persistence (e.g., high scores) or more advanced UI libraries if desired.

---

## Troubleshooting

- If you see an error about ES modules or import paths, ensure you are running Node >= 18 and that package.json contains "type": "module".
- If colors don't display correctly in your terminal, try a different terminal emulator or remove color wrappers in src/colors.js.

---

## License

MIT — see package.json for license information.

---

If you'd like, I can create the README.md file in a new branch for you.