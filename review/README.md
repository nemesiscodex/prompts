# PR Reviewer Prompt

A system prompt that provides a structured approach for comprehensive pull request reviews with certainty ratings. Compatible with any AI coding assistant (Cursor, Claude Code, OpenCode, Codex, etc.).

## Quick Setup (Cursor)

**For project-specific commands:**
```bash
mkdir -p .cursor/commands
cp review.md .cursor/commands/review.md
```

**For global commands (available across all projects):**
```bash
mkdir -p ~/.cursor/commands
cp review.md ~/.cursor/commands/review.md
```

## Usage

Copy the contents of `review.md` and use it as a system prompt or instruction for your AI coding assistant. The prompt can be:

- Added as a system message/instruction in your AI assistant
- Saved as a custom prompt/command in your tool's configuration
- Used directly in a conversation to guide the AI's review process

**For Cursor users:**
1. Type `/` in the Cursor chat input box to see available commands
2. Select `/review` (or whatever you named the command file)
3. (Optional) Add additional context after the command, e.g., `/review against master branch as base, use the full diff`

**Example usage:**
- "Review the PR" or `/review` - Review the current PR
- "Review the PR against main branch" or `/review against main branch` - Review PR against main branch
- "Review the PR using develop as base" or `/review using develop as base` - Review PR using develop as base

The AI will respond with "👮‍♂️ Reviewing PR" and provide a structured review with:
- 0-100% certainty scores for each comment
- Reasoning behind feedback
- Final ratings for Code Quality, Testing Coverage, Readability, and Overall Rating (1-10)

## What It Does

The PR Reviewer command follows a systematic 10-step review process:

1. **Tools Available**: Uses git MCP server or git commands to gather PR information
2. **Understand the Context**: Reads the full diff, PR description, and linked issues
3. **Perform Automated Analysis**: Runs static analysis tools (if provided) with certainty scores
4. **Consider Alternative Approaches**: Evaluates at least three approaches with pros and cons
5. **Identify Bugs and Weirdness**: Checks for logical errors, runtime issues, and code smells
6. **Conduct a Focused Line-by-Line Review**: Targets critical or complex sections
7. **Evaluate Readability and Maintainability**: Ensures code is clear, organized, and well-documented
8. **Verify Testing Coverage**: Confirms tests are included and identifies missing test cases
9. **Provide Constructive Feedback**: Compiles findings into clear, prioritized comments
10. **Final Pull Request Rating**: Assigns ratings for Code Quality, Testing Coverage, Readability, and Overall Rating

