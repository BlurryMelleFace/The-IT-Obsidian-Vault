---
tags:
  - agile
  - scrum
  - methodology
  - framework
  - process
---

# Scrum Framework

> [!INFO]
> **Scrum** is a lightweight framework for solving complex problems by delivering value iteratively. It relies on **empiricism** and is sustained by five **values**: commitment, focus, openness, respect, and courage.

**Related Notes:**
- [[PBI (Product Backlog Item)]] – The core unit of work.
- [[BUG]] – How to handle defects.

---

## 1) Scrum Team

A **cohesive, self-managing** team focused on one objective at a time: the **Product Goal**.

|Role|Accountabilities|Typical Activities|
|---|---|---|
|**Product Owner**|Maximizes product value; manages the **Product Backlog**.|Define Product Goal, order backlog, clarify value and outcomes.|
|**Scrum Master**|Establishes Scrum as defined; enables effectiveness; facilitates.|Remove impediments, coach team/org in Scrum, foster empiricism.|
|**Developers**|Create any aspect of a **usable Increment** each Sprint.|Plan work, build/test/integrate, adapt the Sprint Backlog daily.|

> **Team size:** Typically **10 people or less**.

---

# 2) Empirical Process Control

**Pillars**

- **Transparency** – Work and process are made visible to those doing/receiving it.
    
- **Inspection** – Artifacts and progress toward goals are inspected frequently.
    
- **Adaptation** – Adjust process/materials when variances or issues are detected.
    

**Values**

- **Commitment · Focus · Openness · Respect · Courage**
    

---

# 3) Scrum Events (Time‑boxed)

**The Sprint** (1 month or less): container event that delivers a **usable Increment** toward the **Sprint Goal** (a concrete step toward the Product Goal). It includes four formal events:

## 3.1 Sprint Planning

- **Purpose:** Decide **why** the Sprint matters, **what** can be done, and **how** it will get done.
    
- **Key Topics:**
    
    1. _Why is this Sprint valuable?_ (Sprint Goal)
        
    2. _What can be done this Sprint?_ (selected Product Backlog Items)
        
    3. _How will the chosen work get done?_ (plan by Developers)
        
- **Participants:** Entire Scrum Team
    
- **Timebox (4‑week Sprint):** up to **8 hours**
    
- **Outcome:** Sprint Goal + Sprint Backlog
    

## 3.2 Daily Scrum

- **Purpose:** Inspect progress toward the Sprint Goal and **adapt** the Sprint Backlog.
    
- **Participants:** Developers
    
- **Timebox:** **15 minutes or less**
    
- **Outcome:** Sprint Backlog adjustments / next 24h plan
    

## 3.3 Sprint Review

- **Purpose:** Inspect the outcome with stakeholders; adapt the Product Backlog.
    
- **Participants:** Scrum Team + key stakeholders
    
- **Timebox (4‑week Sprint):** up to **4 hours**
    
- **Outcome:** Product Backlog adjustments
    

## 3.4 Sprint Retrospective

- **Purpose:** Plan ways to **increase quality and effectiveness** next Sprint.
    
- **Discuss:** What went well; problems; how they were (or weren’t) solved; improvements.
    
- **Participants:** Scrum Team
    
- **Timebox (4‑week Sprint):** up to **3 hours**
    
- **Outcome:** Concrete improvement actions (often added to next Sprint Backlog)
    

> **Note:** Timeboxes scale down with shorter Sprints. The values above are for a **4‑week** Sprint.

---

# 4) Scrum Artifacts & Commitments

|Artifact|What it represents|Commitment|
|---|---|---|
|**Product Backlog**|Emergent, ordered list of what’s needed to improve the product.|**Product Goal** – a target future state of the product.|
|**Sprint Backlog**|Plan by/for Developers: selected work for the Sprint + plan to deliver it.|**Sprint Goal** – the single objective for the Sprint.|
|**Increment**|The whole product’s current state; sum of all completed work in the Sprint.|**Definition of Done** – quality bar indicating when work is complete.|

### Definitions

- **Product Goal:** A future state of the product that the Scrum Team plans against.
    
- **Sprint Goal:** The single, coherent objective for the Sprint; guides the team’s work.
    
- **Definition of Done (DoD):** Formal description of quality measures required for an Increment to be considered complete; applies to all selected work.
    

---

# 5) Practical Agendas & Checklists

## 5.1 Sprint Planning – Quick Agenda

- Confirm Product Goal alignment
    
- Draft Sprint Goal (_why valuable now_)
    
- Select items (forecast) and slice if needed
    
- Outline implementation plan (_how_)
    
- Identify risks, dependencies, capacity signals
    

**Checklist**

-  Sprint Goal expresses value & outcome
    
-  Items are clear enough to start
    
-  Plan includes a first‑day walking skeleton
    

## 5.2 Daily Scrum – Prompts

- Where are we relative to the **Sprint Goal**?
    
- What’s the most valuable thing to finish **today**?
    
- What adjustment do we need in the plan?
    

## 5.3 Sprint Review – Quick Agenda

- Demo **done** Increment(s) only
    
- Inspect outcomes vs. Sprint Goal
    
- Discuss value, risks, next options with stakeholders
    
- Update Product Backlog and forecast
    

## 5.4 Sprint Retrospective – Prompts

- What helped us deliver?
    
- What slowed or surprised us?
    
- What one change would most improve effectiveness/quality next Sprint?
    
- Decide 1–3 actionable experiments; add to next Sprint Backlog if appropriate
    

---

# 6) Templates (Copy‑Paste)

## 6.1 Sprint Goal (template)

```md
**Sprint Goal** — <concise outcome/value>
Constraints/Notes: <risks, dependencies>
Measures of success: <signals or metric>
```

## 6.2 Definition of Done (example skeleton)

```md
**Definition of Done**
- Code implemented, peer‑reviewed
- Tests added/passing (unit/integration)
- Security/lint checks green
- Docs updated (user & technical)
- Deployed to <env>; feature flag/rollback ready
```

---

> **Remember:** The Sprint Goal is a **value‑oriented outcome**, not a task list. The Increment is the **whole product** at a new state, meeting the **DoD**.