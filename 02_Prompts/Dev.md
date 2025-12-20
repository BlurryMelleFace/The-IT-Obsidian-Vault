---
tags:
  - prompts
  - dev
  - coding
  - git
  - documentation
---

# Development Prompts

> [!INFO]
> A collection of useful prompts for daily development tasks, from polishing text to analyzing code.

## ✍️ Polishing & Formatting
```text
Please polish this prompt:
```

```text
Please convert this phrase into an underscore-separated format: "partofword_partofword_partofword," ensuring all words are joined with underscores:
```

```text
Please be concise.
```

## 🌿 Git & Reviews
**Merge Request Summary:**
```text
Please summarize this `.diff` file for use as a merge request description.

Audience: developers/colleagues.
Format: markdown (for Git merge/PR description).

Please structure the summary as follows:
1. High-level summary paragraph.
2. Sections:
   - ✅ Added
   - ♻️ Refactored
   - 🧹 Cleanups
3. 📁 Changed Files Overview: as a markdown table with filename, additions, and deletions.
4. End with a sentence about the goal or future context of the changes.

Keep it concise, professional, and ready to paste into a Git merge description.
```

**Merge Request Reviewer:**
```text
# Merge Request Review Assistance Prompt

I am currently conducting a **merge request review** and would like your expert assistance in evaluating it thoroughly.

Please:
1. **Explain what is happening** in the provided merge request — summarize the key changes, their purpose, and how they impact the project.
2. **Identify areas for improvement**, both in terms of code quality (e.g., structure, readability, efficiency) and adherence to best practices (e.g., maintainability, security, and consistency).
3. **Offer constructive feedback** on how the implementation could be enhanced or made more robust.

Your response should be clear, professional, and actionable, with concise explanations and practical recommendations.

---
**Goal:** Achieve a well-informed and insightful merge request review that helps ensure clean, efficient, and maintainable code.
```

## 📄 Documentation (README)
```text
Please revise and enhance the README file to ensure it accurately reflects the current state and structure of the repository. The updated version should:

- Be thoroughly reviewed for grammar, spelling, and clarity.
- Include up-to-date descriptions of all key components, features, and usage instructions.
- Follow a professional and consistent tone throughout.
- Be well-organized with appropriate headings, formatting, and code examples if necessary.

The goal is to produce a comprehensive and polished README that effectively communicates the purpose and functionality of the project to both technical and non-technical audiences. Kindly provide the improved prompt in a downloadable Markdown file format. Thank you!
```

## 🔍 Analysis & Explanation
**List Files:**
```text
Please have a look at the image. Please list all the files in the following manner and return it as a md bash:

**`file`**
```

**JSON Tree:**
```text
Generate a Bash-style tree representation of the JSON structure. Use '[array]' to indicate lists, keep indentation levels clear, and show nested structures accurately. If a list contains objects, show only the structure of the first item.
```

**File Relationships:**
```text
Please explain the relationship between these files. This information is crucial, as I will need it for another prompt. Ensure clarity, precision, and conciseness. Please return it as a md bash for easy copying.
```

**UI/Task Visualization:**
```text
Create a clear, visually structured UI representation of the provided tasks based on the PBIs and acceptance criteria. Present a professional visualization that groups tasks logically and shows their workflow and hierarchy. Briefly explain how each task and its acceptance criteria contribute to the sprint goal. Include a short section mapping each PBI to its impact on the sprint goal and the value it delivers. Use polished, concise language and standard UI/UX patterns (e.g., cards, columns, flows) to ensure maximum clarity.
```

## 🤖 Meta-Prompting (Improving Prompts)
```text
Please refine and elevate the quality of my prompt while maintaining its original purpose. Improve its clarity, structure, and level of detail to ensure precise and seamless comprehension. The final version should be impeccably written, professionally organized, and enriched with descriptive language to optimize understanding for a chatbot. Kindly provide the improved prompt in a downloadable Markdown file format.
```

## 🧙‍♂️ Code Generation Guidelines
```text
Ensure all changes you make are fully aligned with the current repository structure and established conventions. Before implementing modifications, carefully analyze the repository’s layout, files, and coding patterns to understand its logic and dependencies. Incorporate updates that maintain consistency, readability, and quality, avoiding any structural or stylistic deviations. All changes must integrate seamlessly into the existing system, enhancing functionality while preserving the repository’s integrity and coherence.
```
