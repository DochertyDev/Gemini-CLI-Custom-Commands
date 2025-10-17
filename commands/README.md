# Custom Command Configuration

This directory contains the `.toml` files that define custom commands for the Gemini CLI. These commands often reference a `.context` directory, which is expected to exist in the root of your project.

## The `.context` Directory

The `.context` directory serves as a dedicated workspace for the Gemini CLI, holding template files that provide context or store output for various commands. This allows the CLI to operate on a set of known files without cluttering your project's root directory.

Below are the files commonly referenced by the commands and their intended purpose:

### `changeLog.md`

- **Purpose**: Stores a running log of project changes.
- **Used By**: The `changelog` command.
- **Description**: This file is amended by the `changelog` command to include a summary of recent code modifications, new features, and bug fixes, maintaining a history of the project's evolution.

### `newError.md`

- **Purpose**: Captures the details of an error for investigation.
- **Used By**: The `error` command.
- **Description**: When you encounter a bug or an error, its output or description should be placed in this file. The `error` command then uses this context to begin its debugging and resolution process.

### `newTaskInstructions.md`

- **Purpose**: Holds the strategic plan for a new task or feature.
- **Used By**: The `plan` command.
- **Description**: The `plan` command generates a detailed, step-by-step strategic plan to address a user's goal. This plan is written to `newTaskInstructions.md` to guide the subsequent implementation work.

### `styleGuide.md` & `uxRules.md`

- **Purpose**: Define the visual and user experience standards for a project.
- **Used By**: The `uiheal` command.
- **Description**: These files establish the foundational guidelines for frontend design. `styleGuide.md` should contain rules about colors, typography, and spacing, while `uxRules.md` should define standards for user interaction and component behavior. The `uiheal` command uses them as a source of truth to grade and correct UI inconsistencies.
