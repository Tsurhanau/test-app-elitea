# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts. The application runs in a terminal, presents multiple-choice questions, provides immediate feedback and explanations, and displays a final score with review of incorrect answers.

## Project Overview

Quiz CLI is a dependency-free Node.js application built with native ES modules. It is designed both as a small educational game and as an example of modern JavaScript fundamentals, including:

- Interactive terminal input with Node.js `readline`.
- Category and question-count selection.
- Randomized question order using the Fisher–Yates algorithm.
- Progress indicators, ANSI terminal colors, and immediate answer feedback.
- Explanations for quiz answers and incorrect-answer review.
- Replay support after each quiz.
- Examples of async/await, Promises, classes, destructuring, array methods, and file-system operations.

The included question bank contains JavaScript Basics, Node.js Fundamentals, and General Programming categories.

## Setup Instructions

### Prerequisites

- Node.js 18 or later.
- npm (included with Node.js).
- A terminal that supports standard ANSI color escape codes.

### Installation

```bash
git clone https://github.com/Tsurhanau/test-app-elitea.git
cd test-app-elitea/test-app
npm install
```

The project has no third-party runtime dependencies, so `npm install` primarily validates the project and creates npm metadata if needed.

## Usage Examples

### Start the quiz

```bash
npm start
```

Alternatively, run the entry point directly:

```bash
node index.js
```

Follow the prompts to choose a category, select the number of questions, answer each multiple-choice question by entering its number, and review your results. Choose `y` when asked if you want to play again.

## File Structure

```text
test-app/
├── data/
│   └── questions.json    # Categories, questions, choices, answers, and explanations
├── src/
│   ├── colors.js         # ANSI color and text-style helpers
│   ├── input.js          # Readline prompts, selection, confirmation, and pause helpers
│   └── quiz.js           # Quiz state, scoring, shuffling, progress, and results
├── index.js              # Application entry point and main quiz loop
├── package.json          # Project metadata, scripts, and Node.js requirement
└── README.md             # Project documentation
```

## Configuration and Content

Quiz content is stored in `data/questions.json`. Each category provides a display name and a list of questions. Each question contains a prompt, an `options` array, a zero-based `answer` index, and an optional explanation. To add or revise questions, edit that JSON file while preserving this structure.

## Testing

The package defines a test command:

```bash
npm test
```

At present, the repository does not include test files, so the command is primarily a placeholder for future Node.js tests.

## Development Notes

- The package uses ES modules (`"type": "module"`), so imports use `import`/`export` syntax.
- No external packages are required; the application uses Node.js built-in modules only.
- Questions are loaded relative to `index.js`, allowing the application to be launched from the project directory without relying on the current working directory.
- The `__MACOSX` metadata files and `.DS_Store` files are archive/operating-system artifacts and are not needed to run the application.

## License

This project is released under the [MIT License](https://opensource.org/licenses/MIT), as declared in `package.json`.