# Genies-Lamp: Project Specification

## 1. Problem Statement

As a Gemini CLI user, I want to define a set of custom, file-based commands that I can invoke within the CLI. Invoking a command should load a specific persona and protocol for Gemini to follow, allowing for consistent and repeatable interactions tailored to specific tasks. The overall structure and functionality should be inspired by the `baleen37/dotfiles` repository.

## 2. User Interaction Model (UX)

The primary method for invoking a command will be a slash-command interface.

- **Invocation:** The user types a command starting with a forward slash (e.g., `/brainstorm`).
- **Trigger:** The `/` prefix is the designated trigger that tells the system to execute a custom command.
- **Execution:** Upon receiving the command, the system immediately locates the corresponding command definition file, loads it as its new operational context, and begins the interaction as defined in the file.
- **Auto-completion:** While auto-completion is a desired feature for usability, it is recognized as a function of the client-side CLI tool itself and is not a direct implementation responsibility of the command-handling logic.

## 3. Functional Requirements

- **Command Recognition:** The system MUST detect user input that begins with the `/` character as a command invocation.
- **Command File Loading:** The system MUST be able to locate and read the content of a corresponding `.md` file from the pre-defined directory (`/Users/hooooonje/genies-lamp/commands/gemini/`).
- **Persona Adoption:** The content of the loaded `.md` file MUST override the system's current operational instructions, effectively setting a new persona, protocol, and goal for the duration of the task.
- **Command Listing:** The system SHOULD provide a mechanism for the user to discover available commands (e.g., a `/list` or `/help` command).

## 4. Success Criteria

The primary measure of success for this project is the **quality and reliability of the output**, not the speed of the response.

- **Core Metric:** The system must faithfully adhere to the protocols defined in its command files, such as the "Think Hard Protocol." It should prioritize deep thinking, autonomous research, and context-aware questioning to provide well-reasoned, reliable answers and minimize hallucinations. The user must feel that the responses are the product of deep understanding, not superficial pattern matching.

## 5. Edge Cases & Error Handling

- **Non-Existent Command:** If a user enters a command that does not have a corresponding file (e.g., `/non_existent_command`), the system MUST NOT simply return an error. Instead, it SHOULD search for the most similarly named command within the `commands/gemini/` directory and respond with a helpful suggestion, such as, "Command not found. Did you mean `/existing_command`?"
