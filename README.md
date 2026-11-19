# Tic Tac Toe

A browser-based Tic Tac Toe game featuring a human player competing against a simple AI opponent, built using vanilla JavaScript, HTML5 and CSS3.

## Table of Contents

- [Overview](#overview)

- [Features](#features)

- [Screenshots](#screenshots)

- [Live Demo](#live-demo)

- [Tech Stack](#tech-stack)

- [Architecture](#architecture)

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)

  - [Installation](#installation)

- [Project Structure](#project-structure)

- [Available Commands](#available-commands)

- [Development](#development)

- [Testing](#testing)

- [Deployment](#deployment)

- [Troubleshooting](#troubleshooting)

- [Contributing](#contributing)

- [License](#license)

- [Acknowledgements](#acknowledgements)

- [Contact](#contact)

---

## Overview

Tic Tac Toe is a browser-based implementation of the traditional Tic Tac Toe game. It allows one human player to compete against a simple computer-controlled opponent (AI Bot) on a 3 × 3 game board.

The application was developed as a practical exercise to strengthen JavaScript programming skills, particularly in:

- Objects and object-oriented programming.

- Factory functions.

- Closures and private functions.

- Immediately Invoked Function Expressions (IIFE).

- Separation of application logic and presentation.

- DOM manipulation and event handling.

- Basic game-state management.

The project focuses on organising JavaScript code into maintainable components while implementing the functionality of a familiar game.

## Features

- **Human vs AI:** Play against a computer-controlled opponent.

- **Interactive Game Board:** Play using a clickable 3 × 3 grid.

- **Player Identification:** Enter a player name before starting a game.

- **Turn Management:** Alternate between the human player and the AI opponent.

- **Winning Detection:** Identify winning combinations across rows, columns and diagonals.

- **Draw Detection:** Identify when a game ends without a winner.

- **Game Status:** Display the current game status and final result.

- **Winning Conditions Audit:** Display the results of the winning-condition checks.

- **New Game:** Start a new round and reset the game board.

- **Input Validation:** Prevent selecting an already occupied grid position.

## Screenshots

### Game Dashboard

### Active Game

### Game Result

## Live Demo : [Tic Tac Toe – Live Demo](https://amalk.au/tic-tac-toe/)

## Tech Stack

| Category              | Technology                      |
| --------------------- | ------------------------------- |
| Frontend              | HTML5                           |
| Styling               | CSS3                            |
| Programming Language  | JavaScript (Vanilla JavaScript) |
| Architecture          | Factory Functions and IIFE      |
| DOM Manipulation      | JavaScript DOM API              |
| Package Manager       | None                            |
| Build System          | None                            |
| External Dependencies | None                            |

## Architecture

The application follows a modular JavaScript design that separates game state, game logic and user interface interactions.

The implementation consists of three primary components.

### 1\. gameMemory

`gameMemory` is an Immediately Invoked Function Expression (IIFE) responsible for maintaining the application's game state.

It stores:

- Player information, including the player name and marker.

- AI opponent information.

- Player and AI statistics.

- Current game board positions.

- Turn information.

- The identity of the player who made the last move.

The IIFE provides a single shared instance of the game state.

### 2\. gameLogic

`gameLogic` is a factory function responsible for the core game mechanics.

Its responsibilities include:

- Initialising a new game.

- Processing player selections.

- Generating AI opponent moves.

- Managing player turns.

- Checking winning combinations.

- Detecting draws.

- Determining when a game has finished.

The AI opponent currently selects its moves randomly from the available board positions.

### 3\. displayController

`displayController` is responsible for communication between the game logic and the HTML interface.

Its responsibilities include:

- Registering event listeners.

- Capturing player selections.

- Updating the game board.

- Displaying the current game status.

- Displaying the winner or draw result.

- Updating the winning-condition audit.

### Game Flow

The application follows this general execution flow:

1.  The browser loads `index.html`.

2.  The JavaScript application initialises the game state.

3.  The player enters their name and starts a new game.

4.  The player selects an available position on the game board.

5.  The game logic updates the board.

6.  The AI opponent generates a move.

7.  The application checks for winning conditions or a draw.

8.  The interface displays the updated game state.

9.  The game continues until a winner is determined or the game ends in a draw.

### Winning Conditions

A player wins by occupying three positions in a straight line.

The eight possible winning combinations are:

| Combination   | Board Positions |
| ------------- | --------------- |
| Top Row       | 0, 1, 2         |
| Middle Row    | 3, 4, 5         |
| Bottom Row    | 6, 7, 8         |
| Left Column   | 0, 3, 6         |
| Middle Column | 1, 4, 7         |
| Right Column  | 2, 5, 8         |
| Diagonal      | 0, 4, 8         |
| Diagonal      | 2, 4, 6         |

Board coordinate reference:

```
+---+---+---+
| 0 | 1 | 2 |
+---+---+---+
| 3 | 4 | 5 |
+---+---+---+
| 6 | 7 | 8 |
+---+---+---+
```

A draw is intended to occur when all board positions have been occupied without either player satisfying a winning condition.

## Getting Started

### Prerequisites

The application has minimal development requirements.

- A modern web browser (Firefox, Chrome or another standards-compliant browser).

- Git for cloning the repository.

No Node.js runtime, package manager, database or external service is required to run the application.

### Installation

1.  Clone the repository:

    ```
    git clone https://github.com/amalk-au/tic-tac-toe.git
    ```

2.  Navigate to the project directory:

    ```
    cd tic-tac-toe
    ```

3.  Open `index.html` directly in your browser.

    Alternatively, start a local HTTP server using Python:

    ```
    python3 -m http.server 8000
    ```

4.  Open the following address in your browser:

    ```
    http://localhost:8000
    ```

5.  Enter your player name and select **Start New Game** to begin playing.

No additional installation or environment configuration is required.

## Project Structure

```
tic-tac-toe/
│
├── css/
│   └── main.css                 # Application styles
│
├── js/
│   └── main.js                  # Game logic and application behaviour
│
├── docs/
│   └── screenshots/             # Project screenshots (to be added)
│
├── index.html                   # Main application entry point
├── LICENSE                      # GNU GPL v3.0 licence
└── README.md                    # Project documentation
```

## Available Commands

This project is a static HTML, CSS and JavaScript application.

There is currently no `package.json`, package manager configuration or build system.

Consequently, pnpm scripts such as `pnpm install`, `pnpm dev` and `pnpm build` are not applicable to the current implementation.

| Command                                                 | Description                       |
| ------------------------------------------------------- | --------------------------------- |
| `git clone https://github.com/amalk-au/tic-tac-toe.git` | Clone the repository              |
| `cd tic-tac-toe`                                        | Navigate to the project directory |
| `python3 -m http.server 8000`                           | Start a local development server  |

## Development

The project was originally developed to practise JavaScript programming concepts and modular application design.

When modifying the application, consider the following guidelines:

1.  Keep game state management separate from game logic.

2.  Keep DOM manipulation and event handling within the display controller.

3.  Use factory functions to encapsulate reusable application logic.

4.  Use IIFEs when a single application instance is required.

5.  Avoid unnecessary global variables.

6.  Keep the implementation dependency-free unless additional dependencies are genuinely required.

7.  Test game interactions and winning conditions after making changes.

### Development Resources

The application source code is available in:

- `index.html` – Application structure and original technical documentation.

- `js/main.js` – Game logic, state management and display controller.

- `css/main.css` – Application styling.

Browser developer tools can also be used to inspect the application and debug JavaScript execution.

## Testing

The repository does not currently contain an automated testing framework or test suite.

Testing can be performed manually through the browser.

Recommended test scenarios:

| Test Scenario                  | Expected Behaviour                                        |
| ------------------------------ | --------------------------------------------------------- |
| Start a new game               | Game board is reset and player information is initialised |
| Enter a player name            | Player name is stored for the current game                |
| Select an available position   | Player selection is displayed on the board                |
| Select an occupied position    | Application prevents the selection and displays an alert  |
| AI opponent makes a move       | AI selection is displayed on the board                    |
| Complete a winning combination | Application identifies the winner                         |
| Complete a draw                | Application displays a draw result                        |
| Start another game             | Previous board positions and result information are reset |

Use browser developer tools to inspect console messages and identify JavaScript errors.

## Deployment

The application is a static website and does not require a backend server, database or production build process.

### Live Deployment

The application is hosted under the following portfolio domain:

[**https://amalk.au**](https://amalk.au)

Live application:

[**https://amalk.au/tic-tac-toe/**](https://amalk.au/tic-tac-toe/)

### Deployment Requirements

The deployment environment must support serving static files.

The following files and directories must be available:

- `index.html`

- `css/main.css`

- `js/main.js`

### Subdirectory Deployment

The application uses relative asset references:

```
<link rel="stylesheet" href="./css/main.css" />
<script src="./js/main.js"></script>
```

This allows the application to be served from a subdirectory, such as:

```
https://amalk.au/tic-tac-toe/
```

The relative asset paths should be preserved when deploying under a subdirectory.

No build command or environment variables are currently required.

## Troubleshooting

| Issue                                    | Possible Solution                                                             |
| ---------------------------------------- | ----------------------------------------------------------------------------- |
| Application does not load                | Check that `index.html` is accessible                                         |
| CSS styles are missing                   | Verify that `css/main.css` exists and the relative stylesheet path is correct |
| JavaScript functionality is not working  | Check that `js/main.js` is accessible and inspect the browser console         |
| Game board does not update               | Inspect JavaScript errors and verify the game state                           |
| AI opponent does not make a move         | Inspect the AI move-selection logic and available board positions             |
| Changes are not visible after deployment | Clear the browser cache and verify that the latest files have been deployed   |

## Contributing

Contributions, suggestions and improvements are welcome.

To contribute:

1.  Fork the repository.

2.  Create a feature branch.

3.  Implement your changes.

4.  Test the application in a browser.

5.  Commit your changes.

6.  Open a pull request.

For significant changes, consider opening an issue first to discuss the proposed implementation.

## License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

You are free to use, modify and distribute this software under the terms of the licence.

See [LICENSE](LICENSE) for the complete licence text.

## Acknowledgements

- Developed by Amal Kariyawasam.

- Created in March 2024 as a practical JavaScript learning project.

- Inspired by the traditional Tic Tac Toe game.

## Contact

- **Author:** Amal K.

- **GitHub:** [@amalk-au](https://github.com/amalk-au)

- **Portfolio:** [https://amalk.au](https://amalk.au)

- **Repository:** [amalk-au/tic-tac-toe](https://github.com/amalk-au/tic-tac-toe)

- **Issues:** [GitHub Issues](https://github.com/amalk-au/tic-tac-toe/issues)

---

Developed by **amalk-au**
