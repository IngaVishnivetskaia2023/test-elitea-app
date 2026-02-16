# Quiz CLI

An interactive command-line quiz game for learning JavaScript.

## Project description

Quiz CLI is a lightweight Node.js command-line application that provides interactive quizzes across multiple categories (for example: JavaScript Basics, Node.js Fundamentals, and General Programming). It's designed to demonstrate common JavaScript and Node.js features like ES modules, async/await, file system operations, user input handling, classes, array methods, destructuring, template literals, and error handling.

The app loads question data from JSON, presents multiple-choice questions to the user, tracks progress with a simple progress bar, and displays a summary with explanations.

## Setup instructions

Prerequisites:
- Node.js v18 or later
- npm (optional, for dependency management if needed)

1. Clone the repository:

   git clone <repository-url>
   cd <repository-folder>

2. Install dependencies (if any):

   npm install

3. Verify Node.js version (recommended):

   node -v

## How to run the project

Start the quiz from the project root:

npm start

This runs `node index.js` and launches the interactive CLI.

## Key features

- Multi-category quiz questions loaded from data/questions.json
- Interactive command-line prompts and multiple-choice input
- Uses modern JavaScript features (ES modules, async/await)
- Progress tracking and score calculation
- Colorized terminal output for better UX
- Clear result summary with explanations for incorrect answers

## Project structure

- index.js — Main entry point and application loop
- package.json — Project metadata and scripts
- data/questions.json — Question data organized by category
- src/colors.js — Terminal color helpers
- src/input.js — Readline-based user input utilities
- src/quiz.js — Quiz class and core game logic

## Contributing

Contributions are welcome. Suggested workflow:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-change`
3. Commit your changes and push
4. Open a pull request describing your changes

## License

MIT

<!-- EOF -->
