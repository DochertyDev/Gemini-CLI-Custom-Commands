# Available Commands

This directory contains all the custom commands that can be used with the Gemini CLI. The commands are organized into subdirectories based on their function. Each `.toml` file defines a specific command.

### Build

- **`build/dockerize.toml`**: Generates a Dockerfile and docker-compose.yml for the project.
- **`build/implement.toml`**: Executes the implementation plan.

### Design

- **`/design:PRD`** - Creates a an implementation plan based on PRD, UIDD, and SRSD.
- **`design/PRD`**: Creates a Product Requirements Document.
- **`design/SRSD`**: Creates a Software Requirements Specification Document.
- **`design/UIDD`**: Creates a User Interface Design Document.

### Document

- **`document/changelog.toml`**: Create a change log for the recent updates.
- **`document/performance.toml`**: Analyzes the code for potential performance bottlenecks and suggests optimizations.
- **`document/instructions.toml`**: Investigates and creates a strategic plan to accomplish a task.
- **`document/security.toml`**: Performs a comprehensive security audit and generates a vulnerability report.

### Fix

- **`fix/error.toml`**: Investigate an error and perform a fix.
- **`fix/uiheal.toml`**: Capture UI screenshots, grade them against style and UX standards.

### Visualize

- **`visualize/architecture.toml`**: Generates a Mermaid.js diagram to visualize project structure by analyzing the codebase.
- **`visualize/datamodel.toml`**: Generates an Entity-Relationship Diagram (ERD) using Mermaid.js by analyzing database models in the codebase.

---

## Custom Command Configuration

This directory contains the `.toml` files that define custom commands for the Gemini CLI. These commands often reference a `.context` directory, which is expected to exist in the root of your project (it is not included in this repo).

### The `.context` Directory

The `.context` directory serves as a dedicated workspace for the Gemini CLI, holding template files that provide context or store output for various commands. This allows the CLI to operate on a set of known files without cluttering your project's root directory.

Below are the files commonly referenced by the commands and their intended purpose:

#### `changeLog.md`

- **Purpose**: Stores a running log of project changes.
- **Used By**: The `document:changelog` command.
- **Description**: This file is amended by the `changelog` command to include a summary of recent code modifications, new features, and bug fixes, maintaining a history of the project's evolution.

#### `newError.md`

- **Purpose**: Captures the details of an error for investigation.
- **Used By**: The `fix:error` command.
- **Description**: When you encounter a bug or an error, its output or description should be placed in this file. The `error` command then uses this context to begin its debugging and resolution process.

#### `newTaskInstructions.md`

- **Purpose**: Holds the strategic plan for a new task or feature.
- **Used By**: The `document:plan` command.
- **Description**: The `plan` command generates a detailed, step-by-step strategic plan to address a user's goal. This plan is written to `newTaskInstructions.md` to guide the subsequent implementation work.

#### `styleGuide.md` & `uxRules.md`

- **Purpose**: Define the visual and user experience standards for a project.
- **Used By**: The `fix:uiheal` command.
- **Description**: These files establish the foundational guidelines for frontend design. `styleGuide.md` should contain rules about colors, typography, and spacing, while `uxRules.md` should define standards for user interaction and component behavior. The `uiheal` command uses them as a source of truth to grade and correct UI inconsistencies.
