# Gemini CLI Custom Commands

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository is a collection of custom slash commands to extend the functionality of the Gemini CLI, designed to streamline common development workflows.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

Before you can use these custom commands, you must have the Gemini CLI installed.

- **Node.js:** Version 18+ (Version 20+ is recommended).
- **Gemini CLI:** You can install it via npm. For installation instructions, please refer to the [official Gemini CLI documentation](https://github.com/google/gemini-cli).

## Installation

You can install these commands globally (recommended) or for a specific project.

### Global Installation (Recommended)

This method makes the commands available in any project you use with the Gemini CLI.

1. Create the commands directory if it doesn't already exist:

    ```bash
    mkdir -p ~/.gemini/commands
    ```

2. Copy the `.toml` files from this repository's `commands` directory into your `~/.gemini/commands` folder.

### Project-Specific Installation

This method will only make the commands available for the current project.

1. Create the commands directory in your project's root if it doesn't already exist:

    ```bash
    mkdir -p .gemini/commands
    ```

2. Copy the `.toml` files from this repository's `commands` directory into your project's `.gemini/commands` folder.

## Usage

Here are the custom commands included in this repository, organized by category:

### Build

- `/build:dockerize` - Generates a Dockerfile and docker-compose.yml for the project.
- `/build:implement` - Creates a plan and implements based on PRD, UIDD, and SRSD.

### Design

- `/design:PRD` - Creates a Product Requirements Document.
- `/design:SRSD` - Creates a Software Requirements Specification Document.
- `/design:UIDD` - Creates a User Interface Design Document.

### Document

- `/document:changelog` - Create a change log for the recent updates.
- `/document:performance` - Analyzes the code for potential performance bottlenecks and suggests optimizations.
- `/document:plan` - Investigates and creates a strategic plan to accomplish a task.
- `/document:security` - Performs a comprehensive security audit and generates a vulnerability report.

### Fix

- `/fix:error` - Investigate an error and perform a fix.
- `/fix:uiheal` - Capture UI screenshots, grade them against style and UX standards.

### Visualize

- `/visualize:architecture` - Generates a Mermaid.js diagram to visualize project structure by analyzing the codebase.
- `/visualize:datamodel` - Generates an Entity-Relationship Diagram (ERD) using Mermaid.js by analyzing database models in the codebase.

## Contributing

Contributions are welcome! Please follow these steps to add your own custom commands:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeatureName`).
3. Add a new `your-command-name.toml` file to the `commands/` directory.
4. Ensure the `.toml` file has `description` and `prompt` fields.
5. Commit your changes.
6. Push to the branch.
7. Open a Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
