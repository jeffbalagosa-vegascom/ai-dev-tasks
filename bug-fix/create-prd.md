# Rule: Generating a Product Requirements Document (PRD) for Bug Fixes

## Goal

To guide an AI assistant in creating a clear, detailed PRD in Markdown format for **bug fixes**. The goal is to ensure the issue, scope, cause, and resolution steps are fully understood and documented for accurate, reproducible fixes.

## Process

1. **Receive Initial Prompt:** The user provides a brief description or link to a bug or issue (e.g., from Jira, GitHub, etc.).
2. **Ask Clarifying Questions:** Before writing the PRD, the AI *must* ask questions to gather full context. The objective is to clarify **what broke**, **why it matters**, and **how success is defined**. Provide letter/number list options for quick user selection.
3. **Generate PRD:** Based on the user’s input and answers, generate a PRD using the structure outlined below.
4. **Save PRD:** Save as `[n]-bugfix-[short-issue-name].md` in the `/tasks` directory (e.g., `0005-bugfix-login-redirect.md`).

## Clarifying Questions (Examples)

The AI should adapt based on the bug description but generally include:

* **Summary:** "What exactly is broken or not working as expected?"
* **Severity:** "How severe is this issue? (e.g., blocker, critical, minor, cosmetic)"
* **Environment:** "Where was this bug found? (e.g., production, staging, dev, OS/browser/device info)"
* **Steps to Reproduce:** "Can you describe or link to reproduction steps?"
* **Expected Behavior:** "What should have happened?"
* **Actual Behavior:** "What is happening instead?"
* **Frequency:** "Does this occur consistently or intermittently?"
* **Impact:** "Who or what does this bug affect (users, business, systems)?"
* **Root Cause Insight:** "Do we know what caused this yet (if known)?"
* **Proposed Fix/Direction:** "Any initial thoughts on how it might be fixed or verified?"

## PRD Structure

1. **Title/Overview:** Concise title and short paragraph summarizing the issue.
2. **Problem Description:** Clear explanation of what is broken, including user or system impact.
3. **Steps to Reproduce:** Ordered list of steps to consistently replicate the issue.
4. **Expected vs. Actual Behavior:** Side-by-side or bullet comparison.
5. **Environment Details:** Include OS, device, browser, app version, or branch.
6. **Severity & Priority:** Define impact level and urgency.
7. **Root Cause (If Known):** Brief technical description of the underlying issue.
8. **Proposed Fix:** Description of the expected solution (if known) or constraints for the fix.
9. **Acceptance Criteria:** Clear, testable conditions for confirming the bug is resolved.
10. **Dependencies:** Mention related modules, APIs, or third-party services.
11. **Regression Risks:** Identify potential areas that might break due to this fix.
12. **Verification Plan:** Outline steps or tests for QA and developer verification.
13. **Success Metrics:** Define what confirms this bug is fixed and stable (e.g., 100% repro success eliminated, no related tickets reopened for X days).
14. **Attachments/References:** Include screenshots, logs, issue links, or related PRs.

## Target Audience

Assume the PRD reader is a **junior developer or QA engineer**. Requirements must be explicit, concise, and include reproducible details to eliminate ambiguity.

## Output

* **Format:** Markdown (`.md`)
* **Location:** `/tasks/`
* **Filename:** `[n]-bugfix-[short-issue-name].md`

## Final Instructions

1. Do **not** begin implementation until the bug is fully documented and confirmed reproducible.
2. Always include **steps to reproduce** and **acceptance criteria**.
3. If the root cause is unknown, note that clearly and mark the PRD as **diagnostic pending**.
