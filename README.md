# Genie's Lamp

"Genie's Lamp" is your personal AI assistant, designed to empower your development workflow directly from the command line. Inspired by the `baleen37/dotfiles` project, Genie's Lamp allows you to invoke specialized AI personas and workflows for various software engineering tasks, ensuring consistent, high-quality interactions.

## Project Goal

To provide a set of custom, file-based commands that, when invoked within the Gemini CLI, load specific personas and protocols for Gemini to follow. This transforms vague requirements into precise, actionable outcomes, making your development process more efficient and reliable.

## Guiding Principles

All AI interactions and command definitions are governed by the principles outlined in [`gemini.md`](./gemini.md). This file serves as the foundational instruction set for the AI, ensuring all contributions are consistent, high-quality, and aligned with the project's objectives.

## Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/jerrygoha/genies-lamp.git
    cd genies-lamp
    ```

2.  **Add `bin` directory to your PATH:**
    To make `genie` commands accessible from anywhere, add the `bin` directory to your shell's `PATH` environment variable. Add the following line to your shell configuration file (e.g., `~/.zshrc`, `~/.bashrc`, `~/.profile`):
    ```bash
    export PATH="$(pwd)/bin:$PATH"
    ```
    After adding, reload your shell configuration:
    ```bash
    source ~/.zshrc # or ~/.bashrc, etc.
    ```

3.  **Ensure Gemini CLI Integration:**
    This project is designed to work with the Gemini CLI. The commands defined here will instruct the Gemini model on how to behave. Ensure your Gemini CLI is configured to allow dynamic persona and workflow loading based on the content of these `.md` files.

## How to Use

Once set up, you can invoke commands by typing `/` followed by the command name directly in your Gemini CLI session. For example, to start a brainstorming session, you would type:

`/brainstorm`

## Available Commands

Each command loads a specific AI persona and workflow, guiding the interaction to achieve a particular objective. Click on the command name for detailed documentation.

| Command Name | Persona | When to Use |
| :----------- | :------ | :---------- |
| [`brainstorm`](./commands/gemini/brainstorm.md) | 숙련된 제품 전략가이자 AI 엔지니어 | 새로운 프로젝트/기능 아이디어가 막연할 때, 요구사항을 명확히 하고 싶을 때, 구체적인 계획/명세서를 만들고 싶을 때. |
| [`build`](./commands/gemini/build.md) | 체계적인 소프트웨어 엔지니어 | 복잡한 개발 작업(기능 개발, 버그 수정, 리팩토링)을 체계적인 6단계 워크플로우에 따라 진행하고 싶을 때. |
| [`clear`](./commands/gemini/clear.md) | 꼼꼼하고 정확한 버전 관리 도우미 | 현재 Git 리포지토리의 `main` 브랜치를 원격 저장소와 동기화하고 싶을 때, 새로운 작업을 시작하기 전에 깨끗한 기반을 마련하고 싶을 때. |
| [`create-plan-gh`](./commands/gemini/create-plan-gh.md) | GitHub CLI(`gh`) 전문가인 선임 소프트웨어 엔지니어 | GitHub Issues를 사용하여 프로젝트 계획을 수립하고 싶을 때, `gh` CLI를 활용하여 이슈를 빠르고 효율적으로 생성하고 싶을 때. |
| [`create-plan-jira`](./commands/gemini/create-plan-jira.md) | 노련한 애자일 실무자이자 Jira 전문가 | Jira 내에서 상세하고 계층적인 프로젝트 계획을 수립하고 싶을 때, `mcp` CLI 도구를 사용하여 Jira 이슈를 효율적으로 생성하고 싶을 때. |
| [`create-plan`](./commands/gemini/create-plan.md) | TDD와 애자일 방법론을 실천하는 경험 많고 실용적인 선임 소프트웨어 엔지니어 | 사용자 제공 명세서로부터 포괄적이고 단계별 프로젝트 계획을 만들고 싶을 때, 계획을 작고 테스트 가능한 작업으로 분해하고 싶을 때. |
| [`create-pr`](./commands/gemini/create-pr.md) | 꼼꼼한 소프트웨어 엔지니어 | 현재 작업 중인 기능 브랜치에 대해 고품질의, 리뷰 준비가 된 Pull Request를 생성하고 싶을 때. |
| [`create-worktree`](./commands/gemini/create-worktree.md) | 워크트리를 사용하여 효율적인 병렬 개발을 전문으로 하는 Git 워크플로우 전문가 | 주어진 작업을 위해 새롭고 깨끗한 Git 워크트리를 생성하고 싶을 때, 프로젝트의 브랜치 명명 규칙 및 컨벤션을 따르는 워크트리를 만들고 싶을 때. |
| [`do-issue`](./commands/gemini/do-issue.md) | GitHub 이슈 해결에 집중하는 근면하고 체계적인 소프트웨어 엔지니어 | 주어진 GitHub 이슈를 체계적으로 해결하고 싶을 때, 이슈 분석, 계획 수립, 구현, 테스트, PR 제출까지의 전체 워크플로우를 따르고 싶을 때. |
| [`do-todo`](./commands/gemini/do-todo.md) | `todo.md` 파일에서 계획된 작업을 체계적으로 실행하는 방법론적인 개발자 | `todo.md` 파일에 있는 할 일 목록을 순차적으로 실행하고 싶을 때, 각 할 일을 GitHub 이슈와 연결하고 싶을 때. |
| [`fix-pr`](./commands/gemini/fix-pr.md) | Pull Request 문제를 체계적으로 해결하여 병합 준비 상태로 만드는 숙련된 DevOps 엔지니어 | 주어진 Pull Request (또는 현재 브랜치의 PR)에서 모든 미해결 문제(병합 충돌, CI 실패, 리뷰 피드백)를 해결하고 싶을 때. |
| [`make-github-issue`](./commands/gemini/make-github-issue.md) | 코드 리뷰 및 기술적 문제 식별에 깊은 전문 지식을 가진 선임 소프트웨어 엔지니어 | 제공된 코드를 분석하여 식별된 문제에 대한 잘 구조화된 GitHub 이슈를 생성하고 싶을 때. |
| [`session-summary`](./commands/gemini/session-summary.md) | 꼼꼼한 세션 분석가 | 현재 진행 중인 대화 세션의 핵심 지표, 수행된 작업, 통찰력을 요약하여 기록하고 싶을 때. |
| [`setup`](./commands/gemini/setup.md) | 지능적이고 자율적인 AI 개발자 도우미 | 새로운 프로젝트를 시작하거나 기존 프로젝트에 참여할 때 프로젝트의 기술 스택, 명령어, 워크플로우를 자동으로 파악하고 싶을 때. |
| [`update-command`](./commands/gemini/update-command.md) | 세계적 수준의 프롬프트 엔지니어링 전문가 | 기존 프롬프트를 개선하고 싶을 때, 프롬프트의 명확성, 구조, 일관성을 높이고 싶을 때. |
| [`update-docs`](./commands/gemini/update-docs.md) | 세부 사항에 대한 예리한 안목을 가진 선임 소프트웨어 아키텍트 | 리포지토리 전체를 분석하여 문서화의 누락, 부정확성, 불일치를 식별하고 싶을 때. |
