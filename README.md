# wiki-ai
🤖 An AI-driven QA tool to automatically generates test cases from Azure DevOps user stories and bugs, syncs them back to ADO, and exports comprehensive evidence reports.

## 🧠 Copilot Prompt Engineering & System Instructions

To get the most accurate, structured, and comprehensive test cases from GitHub Copilot, use the system instructions and prompt templates below.

### 📋 Copilot System Instructions (.github/copilot-instructions.md)
If you are using Copilot Chat, you can add these instructions to your repository to enforce the output format automatically:

```markdown
You are an expert QA Automation Engineer and Test Designer. 
When generating test cases from Azure DevOps user stories or bugs:
1. Always output test cases in a structured format: ID, Title, Pre-conditions, Steps, and Expected Results.
2. Include Happy Path (positive), Negative, and Boundary/Edge cases.
3. Keep steps clear, concise, and atomic.
4. Ensure the output is ready to be parsed and synced back to the Azure DevOps API.
```

### ⚡ Prompt Templates

#### 1. For User Stories & Acceptance Criteria
> **Prompt:** 
> "Act as a QA Engineer. Read the following Azure DevOps User Story and Acceptance Criteria, and generate a comprehensive suite of test cases. Format them as a JSON array containing objects with `title`, `preconditions`, `steps` (array), and `expectedResult` so they can be synced to ADO.
> 
> [Paste ADO User Story & AC here]"

#### 2. For Bug Reports
> **Prompt:** 
> "Analyze this Azure DevOps Bug Report. Generate a regression test case to verify the fix, and 2 additional edge-case test cases to ensure no related functionality is broken. Format as a markdown table.
> 
> [Paste ADO Bug Details & Steps to Reproduce here]"

### 📊 Evidence Report Prompt
To generate your stakeholder-ready coverage and evidence report after the test cases are finalized, use this prompt:

> **Prompt:**
> "Based on the test cases generated above, create a Test Design Evidence Report in Markdown. Include a 'Coverage Summary' section showing the breakdown of positive vs. negative tests, a 'Requirements Traceability Matrix' mapping the tests to the ADO Story ID, and an 'Assumptions' section."
