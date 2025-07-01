# gemini.md

> **Last Updated:** 2025-07-02
> **Version:** 1.0
> **For:** Gemini CLI (`genie`)

This document provides essential guidelines for Gemini when working with the `genies-lamp` repository. Your primary role is to understand, maintain, and extend the command system for the `genie` CLI tool.

## Repository Overview

This repository contains the `genie` CLI, a tool designed to execute complex, multi-step tasks through AI-powered commands.

### Key Directories

-   `bin/`: Contains the main executable scripts (`genie`, `genie-create-review`).
-   `commands/`: Contains the prompt definitions for all AI commands, organized by model.
    -   `commands/gemini/`: **Your primary workspace.** This is where all prompts for Gemini-powered commands are stored as Markdown files.
-   `spec.md`: The high-level specification for the project.
-   `gemini.md`: **This file.** Your foundational instruction set.

## Core Mission

Your main goal is to assist in the development and maintenance of the `genie` CLI by creating and refining the command prompts located in `commands/gemini/`.

### Development Workflow

1.  **Understand the Goal:** When asked to create or update a command, first analyze the user's request to understand the core objective.
2.  **Review Existing Commands:** Before writing a new command, review 2-3 existing files in `commands/gemini/` to understand the established style, structure, and tone.
3.  **Create or Update:**
    -   **Update:** Read the target Markdown file and apply the requested changes, adhering to the principles in this guide.
    -   **Create:** Create a new Markdown file in `commands/gemini/`. Use the **Command Prompt Template** below as a starting point.
4.  **Verify:** After creating or updating, review your work against the **Quality Checklist** to ensure it is clear, concise, and effective.

---

## Command Prompt Design Guide

Effective command prompts are the foundation of this CLI. Follow these principles to ensure your prompts are robust, consistent, and powerful.

### Core Principles

1.  **Specificity and Clarity**: Define the exact output and format required. Use concrete examples and avoid ambiguity.
2.  **Structured Information**: Structure prompts hierarchically. Start with the persona/role, then state the objective, and finally list all constraints and warnings.
3.  **Layered Techniques**: Combine multiple prompting techniques (e.g., role-playing, few-shot examples, chain-of-thought) to guide the AI effectively.

### Essential Prompting Techniques

#### 1. Role-Based Prompting (Persona)

Clearly define the expert persona the AI should adopt.

> **Example:**
> `You are an expert software engineer specializing in cloud infrastructure and Git workflows. You prioritize clear, maintainable code and thorough documentation.`

#### 2. Chain-of-Thought (CoT)

Instruct the AI to think step-by-step before providing an answer. This improves reasoning for complex tasks.

> **Example:**
> `Before you begin, think step-by-step about the user's request:
> 1. What is the core problem to solve?
> 2. What are the key constraints and requirements?
> 3. What is the simplest, most robust solution?
> 4. What potential issues could arise and how can they be mitigated?`

#### 3. Few-Shot Examples

Provide clear, contrasting examples of good and bad outputs.

> **Example:**
> `Good commit message: "feat(api): add user authentication endpoint"`
> `Bad commit message: "added login"`

#### 4. Structured Output & Templates

Specify the exact format for the output, using Markdown for structure.

> **Example:**
> `Provide the output in the following format:
>
> #### Plan
> 1.  **Step 1:** A brief description of the first step.
> 2.  **Step 2:** A brief description of the second step.
>
> #### Code
> \`\`\`bash
> # The code for the planned steps
> \`\`\``

#### 5. Constraint-Based Instructions

Use clear, firm language for rules and limitations.

> **Example:**
> `- NEVER modify files outside the specified project directory.
> - ALWAYS use existing patterns found in the codebase.
> - MUST ask for clarification if the request is ambiguous.`

#### 6. Self-Validation Checkpoints

Incorporate a verification step in the AI's process.

> **Example:**
> `Before finishing, verify the following:
> ✓ Does the solution directly address the user's request?
> ✓ Is the code secure and free of vulnerabilities?
> ✓ Are all instructions clear and easy for a human to follow?`

---

## Command File Best Practices

Adhere to these standards for all files in `commands/gemini/`.

### 🎯 Maximum Conciseness

-   **Target**: 50-150 lines maximum per command file.
-   **Focus**: Essential information only. Eliminate redundancy.
-   **Format**: Use a quick-reference format (headings, bullets) over long paragraphs.

### 📝 Content and Structure

Your command files should be scannable and actionable.

**Ideal Structure:**

1.  **Persona**: (Required) A clear `You are...` statement.
2.  **Objective**: (Required) A concise summary of the command's goal.
3.  **Core Instructions**: The main logic, using a mix of the prompting techniques described above.
4.  **Constraints & Rules**: A clear list of "DOs" and "DON'Ts".
5.  **Examples**: 1-2 high-quality, practical examples.

### 📋 Quality Checklist for Command Files

Before finalizing any command file, ensure it meets these criteria:

-   [ ] **Concise**: Is the file under 150 lines?
-   [ ] **Persona**: Is there a clear, single-sentence persona definition?
-   [ ] **Clarity**: Is the primary goal unambiguous?
-   [ ] **Constraints**: Are the most critical rules listed?
-   [ ] **Actionable**: Does every section guide the AI toward a specific, correct action?
-   [ ] **Scannable**: Is the content easy to read quickly with headers and bullet points?

---

## Command Prompt Template

Use this template as a starting point for all new commands in `commands/gemini/`.

```markdown
# [Command Name]

You are a [specific, expert persona] who [key traits or priorities].

Your primary goal is to [state the main objective of the command].

### Methodology

Before you begin, think step-by-step to construct a clear plan.
1.  **Analyze**: [First analysis step].
2.  **Plan**: [Second planning step].
3.  **Execute**: [Third execution step].

### Rules & Constraints

-   ALWAYS [critical requirement].
-   NEVER [critical prohibition].
-   MUST [non-negotiable action].
-   If [condition], then [action].

### Output Format

Provide your response using the following Markdown structure:

#### [Section 1]
[Description or content]

#### [Section 2]
[Description or content]

---
*Self-Correction: Before finalizing, review your response to ensure it is accurate, complete, and adheres to all instructions.*
```