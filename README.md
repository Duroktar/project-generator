# Project Generators

This repository contains a collection of bash scripts designed to streamline the creation of various NodeJS project types. It provides a central `project-selector` script that allows you to choose from different pre-configured project setups, automating the initial directory structure, file creation, and dependency installation.

## Features

* **Interactive Project Selection**: Choose your desired project type from a menu.

* **NodeJS Project Generation**: Basic NodeJS project with TypeScript.

* **NodeJS with ANTLR4**: Setup for a NodeJS project integrated with ANTLR4 for grammar parsing. Includes Java check and installation attempt.

* **NodeJS with Blessed.js (2-Panel TUI)**: Generates a NodeJS project with a Blessed.js Terminal User Interface (TUI) featuring a text editor-like panel and a Lorem Ipsum display.

* **Customizable Project Name**: Specify your project name via argument or interactive prompt.

* **Current Directory Default**: Projects are generated in the current working directory by default.

* **Colorized Output**: Optional colored output for better readability in the terminal.

* **Non-Interactive Mode**: A `-y` flag to accept all default inputs for automated setups.

## Installation

To install the `project-selector` script and make it globally accessible (via `~/.local/bin`), run the provided `install.sh` script:

```
./install.sh
```

**Note:** If `~/.local/bin` is not already in your system's `PATH` environment variable, the `install.sh` script will provide instructions on how to add it to your shell's configuration file (e.g., `~/.bashrc` or `~/.zshrc`). After adding, remember to `source` your configuration file or restart your terminal.

## Usage

Once installed, you can run the project selector from any directory:

```
project-selector [PROJECT_NAME] [--color] [-y] [--help]
```

### Arguments:

* `PROJECT_NAME`: (Optional) The name of the project to create. If omitted, you will be prompted to enter it, or a default name (`my-new-project` or `my-antlr4-project` or `my-blessed-tui`) will be used if the `-y` flag is present.

### Flags:

* `--color`: Enables colored output for better readability in the terminal.

* `-y`: Assumes 'yes' to all prompts and uses default values. If `PROJECT_NAME` is not provided, a default name will be used.

* `--help`: Displays a help message and exits.

### Examples:

* **Interactive selection with color:**

```
project-selector --color
```

* **Generate a NodeJS project named 'my-app' non-interactively:**

```
project-selector my-app -y
```

* **Display help:**

```
project-selector --help
```

## Project Types

The `project-selector` currently supports the following project types:

1. **NodeJS**:

 * A basic NodeJS project with TypeScript.

 * Includes `src/index.ts` with a simple `console.log`.

 * Sets up `package.json` with standard scripts (`debug`, `start`, `dev`).

 * Initializes TypeScript configuration (`tsconfig.json`).

2. **NodeJS with ANTLR4**:

 * A NodeJS project pre-configured for ANTLR4 grammar parsing.

 * Includes a check and attempted installation of Java Development Kit (JDK), as ANTLR4 relies on Java.

 * Provides a placeholder ANTLR4 grammar file (`grammar/MyGrammar.g4`).

 * Adds `antlr4` and `antlr4ts` dependencies, and `antlr4ts-cli` for grammar compilation.

 * Includes a `build:grammar` script in `package.json` to compile your grammars.

3. **NodeJS with Blessed.js (2-Panel TUI)**:

 * A NodeJS project designed for building Terminal User Interfaces (TUIs) using Blessed.js.

 * Features a 2-panel layout:

   * **Left Panel**: A Blessed.js `textarea` widget, serving as a text editor-like interface.

   * **Right Panel**: A Blessed.js `box` widget displaying Lorem Ipsum text.

 * Includes `blessed` and `lorem-ipsum` dependencies.

## Contributing

Contributions are welcome! If you have ideas for new project types, improvements to existing ones, or bug fixes, please feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details
