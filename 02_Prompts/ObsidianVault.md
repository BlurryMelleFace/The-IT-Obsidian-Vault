---
tags:
  - obsidian
  - prompts
  - style-guide
  - ai
---

# Obsidian Vault

> [!INFO]
> This note defines the standard prompts and style constraints for generating and refactoring notes within this Obsidian Vault. It serves as the authoritative source for maintaining consistency across the knowledge base.

**Related Notes:**
- [[NotebookLM]] – Prompts specifically designed for NotebookLM interactions.
- [[Dev]] – Development-specific prompts and guidelines.
- [[Index]] – The main entry point for the vault.

---

## 🔑 Core Concepts

To maintain a high-quality knowledge base, all notes must adhere to a strict structure. This ensures that the **knowledge graph** remains interconnected and that content is easily readable and parsable. The prompts below are designed to automate this standardization.

## 🛠️ System Prompts

Use these prompts when instructing AI agents to generate or modify content for the vault.

### New Note Generation

**Goal:** Create a new technical note from scratch that matches the vault's structure.

```text
Topic: 

You are an expert technical writer managing a personal knowledge base in Obsidian. Create a new markdown note for [Topic] following this exact style guide:

1.  Frontmatter: Include a YAML block at the top with relevant tags (lowercase, kebab-case).
2.  Title: H1 Header matching the file name.
3.  Introduction: Immediately follow the title with a > [!INFO] callout block containing a concise definition or summary.
4.  Connections: Add a **Related Notes:** section immediately after the intro. Analyze the entire vault to identify relevant existing notes and ensure proper networking/backlinking to strengthen the knowledge graph. Use the format - [[Note Name]] – Short description of relationship.
5.  Separator: Add a horizontal rule --- after the related notes.
6.  Headings: Use H2 ## and H3 ### headings. ALL H2 headings must start with a relevant emoji
7.  Content Style:
    - Use bold for key terms and concepts.
    - Use code blocks with appropriate language syntax highlighting.
    - Keep paragraphs concise.
    - Use lists for readability.

Output the full markdown code for the note.
```

### Style Enforcement / Refactoring

**Goal:** Rewrite an existing text or rough note to match the vault's style.

```text
MDFile: 

Rewrite the [MDFile] into a clean, structured Obsidian markdown note. Follow this exact style guide:

1.  Frontmatter: Include a YAML block at the top with relevant tags (lowercase, kebab-case).
2.  Title: Ensure there is an H1 Header matching the intended file name.
3.  Introduction: Immediately follow the title with a > [!INFO] callout block containing a concise definition or summary.
4.  Connections: Add a **Related Notes:** section immediately after the intro. Analyze the entire vault to identify relevant existing notes and ensure proper networking/backlinking to strengthen the knowledge graph like in the other documents. Use the format - [[Note Name]] – Short description of relationship.
5.  Separator: Add a horizontal rule --- after the related notes.
6.  Headings: Use H2 ## and H3 ### headings. ALL H2 headings must start with a relevant emoji
7.  Content Style:
    - Use bold for key terms and concepts.
    - Use code blocks with appropriate language syntax highlighting.
    - Keep paragraphs concise.
    - Use lists for readability.
```

## ⚖️ Usage

- **Copy & Paste**: Copy the relevant code block into your AI chat interface.
- **Context**: Provide the specific `[Topic]` or `[MDFile]` content when prompted.
- **Review**: Always review the AI-generated output against the style guide before saving.
