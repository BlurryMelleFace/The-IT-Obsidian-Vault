# **1. High-Level UI Structure of PBIs & Tasks**

## **A. Symbol Creation & Validation Flow**

### _Card Group: “Manual Symbol Addition & Validation”_

**Workflow Overview**

1. **Add Symbol → Draw BBox → Classify → Set Rotation → Add Text → Validate → Save → Highlight on Canvas → Pipeline Propagation**
    

### **Task Flow (visual hierarchy)**

`[Add Symbol Mode]       ↓ [Draw BBox on Canvas]       ↓ [Classification Dropdown]       ↓ [Rotation Selector]       ↓ [Add Associated Text]       ↓ [Validation Checks]       ↓ [Save Symbol]       ↓ [Canvas Highlight]       ↓ [Connection Recognition]       ↓ [DEXPI Mapping]`

### **Acceptance Criteria (summarized)**

- **AC 1–4**: User creates a symbol: BBox, class, rotation, text.
    
- **AC 5–6**: Saving & visual highlighting behave like auto-detected symbols.
    
- **AC 7–9**: Symbol enters full pipeline: connection-recognition & DEXPI export.
    
- **AC 10–15**: Invalid BBoxes rejected; invalid symbols not passed downstream.
    

**Contribution to Sprint Goal:**  
✔ Required for DLS release quality, validates new UI interactions, and ensures pipeline consistency.

---

## **B. Text Association UI (Symbol & Line)**

### _Card Group: “Text Association Enhancements”_

### **Task Flow**

`[Enter Text-Association Mode]       ↓ [Highlight Unassociated Texts]       ↓ [Select Text → Add to Grid]       ↓ [Modify / Accept / Reject]       ↓ [Save Changes]`

### **Acceptance Criteria**

#### **Symbol–Text Association**

- Add new text via BBox.
    
- Modify existing associations without losing links.
    
- Multi-select accept/reject.
    
- Support free text + suggestions.
    
- Re-association logic (text moves from Symbol A → B).
    
- Changes persist to DB.
    

#### **Line–Text Association**

Mirrors symbol logic (association, highlight, selection, re-association, saving).

**Contribution to Sprint Goal:**  
✔ Completes UI components required for OSS Clearing.  
✔ Stabilizes core text-management flows needed before release.  
✔ Moves UI test coverage toward 80%.

---

## **C. File Deletion and Full Cleanup Flow**

### _Card Group: “File Deletion & Cleanup”_

`[Delete Uploaded File]       ↓ [Remove DB Metadata]       ↓ [Remove Stored Files]       ↓ [Remove Processing Jobs]       ↓ [UI Automatically Refreshes]`

### **Acceptance Criteria**

- Delete button is visible and enabled.
    
- All metadata + artifacts + jobs removed.
    
- UI dynamically updates.
    
- No regressions in upload/list/processing flows.
    

**Contribution to Sprint Goal:**  
✔ Required for DLS release-quality robustness.  
✔ Part of OSS finalization (proper cleanup of artifacts).  
✔ Improves UI testability.

---

# **2. Mapped UI Representation (Simplified Sprint Board)**

## **Column 1 — Creation & Editing**

### **Card: Draw & Configure Symbol**

- Draw BBox
    
- Classify symbol
    
- Set rotation
    
- Add associated text
    

### **Card: Validate & Save Symbol**

- Validates bounds + area
    
- Saves symbol
    
- Highlights on canvas
    

---

## **Column 2 — Text Association**

### **Card: Symbol–Text Association**

- Enter mode
    
- Highlight unassociated texts
    
- Select to associate
    
- Re-associate between symbols
    
- Save
    

### **Card: Line–Text Association**

(Same tasks as symbol association)

---

## **Column 3 — Integration & Pipeline**

### **Card: Pass to Connection Recognition**

- Manually added symbol flows into pipeline
    
- Connections detected
    

### **Card: DEXPI Export Mapping**

- Manually added symbol included in DEXPI output
    

---

## **Column 4 — System Maintenance**

### **Card: Delete Uploaded File**

- Remove metadata
    
- Remove file artifacts
    
- Remove job entries
    
- Auto-update UI
    

---

# **3. PBI → Sprint Goal Mapping**

|**PBI**|**Impact on Sprint Goal 36**|**Value Delivered**|
|---|---|---|
|**Manual Symbol Creation & Validation**|Ensures the new DLS release supports complete manual editing flows|Accurate symbol data, fewer false negatives, consistency with automatic pipeline|
|**Symbol & Line Text Association Improvements**|Improves UI correctness and completes remaining OSS Clearing UI requirements|Better control for users, improved data integrity, higher test coverage|
|**Pipeline Integration (Connections + DEXPI)**|Required for release as all modules must support manually created symbols|Full end-to-end traceability, compliance with engineering workflows|
|**Invalid Symbol Handling**|Reduces pipeline errors and ensures data cleanliness|Higher reliability and correctness|
|**File Deletion & Cleanup**|Ensures no stale data remains—critical for OSS and DLS release|Trustworthy file management, clean workspace, easier QA|
|**UI Test Coverage (80%)**|Ensures stability for the release|Reduced regressions, long-term maintainability|

---

# **4. How This Supports Sprint Goal 36**

The sprint's primary goals are:

1. **✔ Release new DLS version with all features completed**  
    → Symbol creation, validation, text association, and pipeline integration satisfy this.
    
2. **✔ Finalize OSS Clearing PBIs**  
    → UI functionality (file deletion, text association flows) completes required components.
    
3. **✔ Achieve 80% UI test coverage**  
    → Clear workflows + predictable UI state enable robust test automation.
    
4. **✔ Enable new line-arrow model in pipeline**  
    → Ensures text association + symbol integration behave correctly with the new model.