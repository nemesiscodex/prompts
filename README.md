# Cursor Custom Instructions

A collection of custom instructions and prompt templates for Cursor, the AI-powered code editor.

## Table of Contents
- [Overview](#overview)
- [Contents](#contents)
  - [PR Reviewer](#pr-reviewer-pr-reviewermd)
- [How to Use](#how-to-use)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository contains specialized instruction sets that enhance Cursor's AI capabilities for specific use cases. These instructions can be copied into Cursor's custom instructions to enable specialized behaviors.

## Contents

### PR Reviewer (`pr-reviewer.md`)

A structured approach for comprehensive pull request reviews with certainty ratings.

**Purpose:**
- Provides a systematic process for reviewing pull requests
- Incorporates certainty scores (0-100%) for each comment
- Includes reasoning behind feedback to improve clarity
- Assigns a final rating for the overall PR quality

**Setup:**
1. Create a new [custom mode](https://docs.cursor.com/chat/custom-modes) in Cursor
2. Name it "PR Reviewer"
3. Add the custom prompt from `pr-reviewer.md`
4. Enable MCP servers you want to use (if using a project-managed MCP server, manually enable it before using this mode)
5. Enable Auto-Run
6. Save the mode

**Review Process:**
0. **Tools Available**: Use git MCP server or git commands to gather PR information (diffs, commit history)
1. **Understand the Context**: Read the full diff, PR description, and linked issues
2. **Perform Automated Analysis**: Run static analysis tools (if provided) with certainty scores
3. **Consider Alternative Approaches**: Evaluate at least three approaches with pros and cons
4. **Identify Bugs and Weirdness**: Check for logical errors, runtime issues, and code smells
5. **Conduct a Focused Line-by-Line Review**: Target critical or complex sections
6. **Evaluate Readability and Maintainability**: Ensure code is clear, organized, and well-documented
7. **Verify Testing Coverage**: Confirm tests are included and identify missing test cases
8. **Provide Constructive Feedback**: Compile findings into clear, prioritized comments
9. **Context-Specific Checks**: Verify performance, security, and UI aspects (if applicable)
10. **Final Pull Request Rating**: Assign ratings for Code Quality, Testing Coverage, Readability, and Overall Rating (1-10)

**Usage:**
- Use the "PR Reviewer" custom mode
- (Optional) Add the PR (diff or commit) as context for the AI
- Request: "Review the PR" or "Review the PR against <main-branch-name> branch" or "Review the PR using <main-branch-name> as base"
- Result: Structured review with 0-100% certainty scores and actionable feedback

## How to Use

1. Follow the specific setup instructions for each instruction set (e.g., PR Reviewer uses custom modes)
2. For instruction sets that use custom modes, create a new custom mode in Cursor and add the provided prompt
3. For instruction sets that use custom instructions, copy the desired instruction set into Cursor's custom instructions
4. Follow the specific usage instructions for each rule file

## Contributing

Feel free to enhance these instructions or add new ones by submitting pull requests.

## License

MIT License

Copyright (c) 2025
