# Obsidian Vault

This repository represents a structured knowledge base managed with [Obsidian](https://obsidian.md/) for the iPID Project at Siemens and other IT related tasks in general. It utilizes both core and community plugins to enhance productivity, note organization, and knowledge retrieval.

## Overview

This vault is a collection of markdown files organized to support development, documentation, and operational processes within the iPID project. It includes structured sections such as:

---
- **00_Secret** – Private credentials and secrets (restricted access)
- **01_Reference** – Technical reference materials (e.g., Git, Docker, FastAPI)
- **02_Promts** – Prompt templates and construction kits
- **03_Projects** – Active and archived project documentation
- **04_Workflows** – Workflow specifications and process documentation
---
- **Index**  – Entry point for the vault
- **README**  – README
---
## Key Features

- **Community Plugins**
  - `dataview`: Query and visualize structured data within your markdown files.
  - `obsidian-git`: Version control with Git integration for your notes.

- **Core Plugins**
  Enabled plugins include:
  - File Explorer, Graph View, Backlinks, Daily Notes, Templates, Outline, etc.

- **Graph Configuration**
  - Tags and attachments are hidden.
  - Orphans are shown to surface disconnected notes.
  - Visual preferences are tuned for clarity and minimalism.

## Usage Instructions

1. **Open the Vault** in Obsidian and ensure plugins are installed and enabled.
2. **Write Notes** using markdown. Use headers and tags for better organization.
3. **Use `dataview` queries** to extract and present structured information.
4. **Commit changes via `obsidian-git`** to preserve version history.

### Example Dataview Query

```dataview
table file.ctime as Created
from "01_Reference"
where contains(file.name, "Docker")
```

## Setup Tips

- Set default view mode to `preview` for readability.
- Appearance theme is `obsidian` (default).
- Custom hotkey: `Alt + C` toggles source view.

## Recommended Workflow

1. Use daily notes for capturing logs and thoughts.
2. Organize references into topic-based subfolders.
3. Tag notes consistently for graph visualization.
4. Commit updates frequently to avoid data loss.

## File Structure Summary

The `.obsidian` folder includes settings for:

- Plugin configurations (`community-plugins.json`, `core-plugins.json`)
- UI preferences and layout (`workspace.json`, `graph.json`)
- Dataview and plugin-specific data (`plugins/dataview/data.json`)

## License

Refer to the `LICENSE` file in the root directory.

## Author

Moritz Staudacher

---

> _“Well-organized knowledge is power.”_
