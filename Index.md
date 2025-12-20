# 🧭 Obsidian Vault Index

Welcome! Use this dynamic index to explore your vault. All content is grouped by category and auto-updated using Dataview.

```dataview
TABLE GIT_USERNAME, GIT_TOKEN
WHERE file.name = "credentials.local"
```
---

## 🔧 01_Reference – Tools & Cheat Sheets

```dataviewjs
const pages = dv.pages('"01_Reference"')
	.groupBy(p => {
	    const folder = p.file.folder;
	    return folder === "01_Reference/" ? "" 
	    : folder.replace("01_Reference/", "");
	});

for (let group of pages) {
    dv.header(3, group.key);
    dv.list(group.rows.map(p => p.file.link));
}
```

---

## 🧠 02_Prompts – Prompt Templates

```dataviewjs
const pages = dv.pages('"02_Prompts"')
	.groupBy(p => {
	    const folder = p.file.folder;
	    return folder === "02_Prompts" ? "" 
	    : folder.replace("02_Prompts/", "");
	});

for (let group of pages) {
    dv.header(3, group.key);
    dv.list(group.rows.map(p => p.file.link));
}
```

---

## 🚧 03_Projects – Work in Progress

```dataviewjs
const pages = dv.pages('"03_Projects"')
	.groupBy(p => {
	    const folder = p.file.folder;
	    return folder === "03_Projects" ? "" 
	    // : folder.replace("03_Projects/", "");
	});

for (let group of pages) {
    dv.header(3, group.key);
    dv.list(group.rows.map(p => p.file.link));
}
```

---

## 📜 04_Workflows – Step-by-Step Guides

```dataviewjs
const pages = dv.pages('"04_Workflows"')
	.groupBy(p => {
	    const folder = p.file.folder;
	    return folder === "04_Workflows" ? "" 
	    : folder.replace("04_Workflow/", "");
	});

for (let group of pages) {
    dv.header(3, group.key);
    dv.list(group.rows.map(p => p.file.link));
}
```

---

