# Command: genie-create-review

**Description:**

This command initiates a code review by:
1.  Extracting the Jira issue key from the current Git branch name.
2.  Fetching the issue details from Jira.
3.  Generating a prompt for Gemini with the issue information and a list of changed files.
4.  Invoking the Gemini CLI to perform the code review.

**Usage:**

```bash
genie-create-review
```

**Dependencies:**

*   `git`: To get the current branch name and changed files.
*   `jira`: The Jira CLI to fetch issue details.
*   `jq`: To parse the JSON output from the Jira CLI.
*   `gemini-cli`: The Gemini CLI to interact with the Gemini model.
