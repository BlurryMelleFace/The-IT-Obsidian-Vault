---
tags:
  - project
  - agile
  - sprint-review
  - planning
---
# What have I done: 

## 2026: 

### **Image & File Processing Pipeline**

- **Unified Processing Task**: You consolidated several functions (PDF-to-image conversion and redlining) into a single, unified `image_processing` / `file_processing` Celery task.
    
- **API De-blocking**: You moved heavy image processing out of the API and into a separate worker, preventing the API from being blocked for long periods (which previously took up to 16 minutes per file).
    
- **Task Chaining**: You implemented Celery task chaining to ensure that file preprocessing is completed before the symbol–text association pipeline begins.
    
- **Redlining Refinement**: You initially removed parameters to enable/disable redlining, choosing to keep it always enabled within the separate task, and later handled a request to temporarily remove it until a dedicated worker was ready.
    

### **Redis & Infrastructure Stability**

- **Redis Migration & Merging**: You tested and merged changes related to Leonardo's merge and Rahul’s Redis changes.
    
- **Failover Research**: You spent significant time simulating and troubleshooting a Redis "read-only" error. You developed a local simulation using master/replica nodes to trigger the error and test a failover mechanism.
    
- **Retry Mechanism**: You identified and configured Celery/Redis retry settings to handle Redis overloads and connection issues.
    
- **Worker Auto-Restart**: You implemented an exit strategy for the worker process when it detects failover errors in the logs, allowing Kubernetes or Docker to automatically spin the pod back up to reconnect.
    

### **Data Analytics & Network Generation**

- **Graph Generation**: You transitioned into the data analytics side, focusing on Python logic and math for network/graph generation.
    
- **DEXPI Output Testing**: You used the PID Verificator to test DEXPI outputs and worked on grid alignment logic.
    
- **Repulsion Algorithm**: You worked on a bug involving symbol spacing, specifically using a "repulsion algorithm" to mitigate overlaps between horizontal and vertical segments.
    

### **Code Quality & Maintenance**

- **SonarQube Cleanup**: You fixed approximately 100 SonarQube issues in a single day to ensure the project passed its Quality Gate.
    
- **Testing Coverage**: You added multiple tests to the image processing task, which significantly improved the overall test score and coverage.
    
- **Documentation**: You introduced Mermaid diagrams to document workflows and the grid logic for better team (and AI/Copilot) understanding.
    

### **UI & Frontend Improvements**

- **System Progress Visibility**: You adjusted the UI to better reflect static processing states so users can see that work is happening.
    
- **Model Update Integration**: You worked on model updates that allowed for selecting word and paper sizes, ensuring this information was properly saved and passed through the repositories.
    
- **Feature Planning**: You prioritized several UI tasks, including a "Middle Mouse Button" drag, a "Ctrl+A" selection mode, and a symbol class dropdown with mini-images.

## 2025: 

### **API Infrastructure & Core Development**

- **FastAPI Migration & Refactoring**: You undertook a massive refactor of the API, moving away from a single "cluttered" `run.py` file to a modular architecture with routers, typed dependencies, and dependency injection.
    
- **Symbol & Text Association Pipeline**: You implemented the initial API pipeline to associate symbols with text, which included mapping word IDs and exchanging text values.
    
- **Sole Task Triggering**: You developed specific endpoints to allow for the independent triggering of detection tasks (symbol, text, and line detection).
    
- **Submit Workflow**: You created the `ipid_recognition_submit` pipeline, which chains together line detection, network generation, and DEXPI file conversion when a user submits their work.
    

### **Data Modeling & Type Safety**

- **Pydantic Integration**: You replaced standard Python dataclasses with Pydantic models across the project to enable better data validation and automatic TypeScript type generation for the frontend.
    
- **Normalized Data Structure**: You redesigned the UI data structure from a "flat" format to a "normalized" one, making it easier to manage complex associations between symbols, lines, and text.
    
- **DEXPI & Schema Mapping**: You worked on the logic to convert data between the backend's internal models and the `PIDSchema` used for DEXPI generation.
    

### **Database & Backend Services**

- **PostgreSQL & Migration**: You performed your first database migration, extending the jobs table to include user identification.
    
- **FDS Integration (Auth & User Service)**: You integrated Siemens FDS (Identity Access Management) to fetch user and tenant information via JWT tokens, ensuring that job data is mapped to the correct user.
    
- **Redis & Celery Stability**: You spent significant time configuring Redis as a message broker for Celery, eventually getting them to work together to handle background tasks reliably.
    

### **Frontend & UI Enhancements**

- **AG Grid Implementation**: You led a "spike" (research task) to implement **AG Grid** in the UI, enabling dynamic filtering, sorting, and better handling of large datasets.
    
- **Siemens Analytics (Matomo)**: You integrated the Siemens Analytics service to track frontend events, such as route changes and button clicks, and established a dashboard for visualization.
    
- **UI Components**: You developed several key UI features, including:
    
    - A language selection dropdown.
        
    - Job deletion icons on the jobs page.
        
    - "Accept" and "Reject" buttons for individual recognition results within the grid.
        
    - An "Unassociated" button for the details page.
        

### **Quality & DevOps**

- **Automated Testing**: You significantly increased test coverage (reaching ~75%) by writing unit tests for core API endpoints and the Backend-for-Frontend (BFF).
    
- **Error Handling Framework**: You moved away from repetitive `try-except` blocks by implementing a global exception handler and a centralized `errors.py` file for domain-specific errors.
    
- **Deployment & Support**: You managed local and remote (Pune machine) environments, fixed Rancher/Docker issues, and assisted other team members (like Georg and Rahul) with their local setups.
- 

## 2024:
### **Initial Project Setup & Infrastructure**

- **Dev Environment Configuration**: You performed the initial cloning of the repositories and configured the local environment using **Python 3.11**, **Poetry**, and **Rancher Desktop** for Kubernetes/Docker management.
    
- **Docker & Helm Automation**: You wrote a **PowerShell (ps1) script** to automate the time-consuming process of creating Docker images, upgrading Helm charts, and managing pod forwarding.
    
- **Poetry & SSH Troubleshooting**: You resolved complex authorization and authentication issues related to Poetry installs and OpenSSH configurations on your new machine.
    

### **API Development & Refactoring**

- **Download & Storage APIs**: You implemented the first API endpoints for folder downloads, utilizing a solution that creates **temporary ZIP files**.
    
- **Image Processing Endpoints**: You developed endpoints to convert images (PNG/JPEG) from storage into **Base64 binary strings** to be returned via JSON.
    
- **SOLID Refactoring**: You performed a major refactor of the existing API functions to adhere to **SOLID principles**, making the codebase more modular and extendable.
    
- **FastAPI Transition**: Following architectural discussions, you migrated the text-recognition public API from **Flask to FastAPI** to ensure better scalability and documentation.
    

### **Symbol & Text Recognition Pipelines**

- **Symbol Classification Integration**: You built the API for uploading and saving symbol classifications into a specific folder and integrated this data into the **UI validation flow**.
    
- **Pipeline Orchestration**: You worked on the **Shared Task** logic to ensure that when a file is uploaded, the system automatically triggers the symbol and text recognition pipelines.
    
- **Celery & Redis Integration**: You integrated **Celery** for background task management and **Redis** as the message broker, implementing features to monitor task status and cancel ongoing tasks.
    
- **PDF to Image Conversion**: You implemented logic in the `recognition-utils` to handle the conversion of PDF files into images before they are passed to the AI models.
    

### **System Maintenance & Support**

- **Storage Cleanup**: You managed the storage directories on the Pune machine, though you noted one instance where an incorrect command accidentally cleared the entire storage folder.
    
- **Global Support**: You assisted fellow students and team members (like Pulkit and Anita) with their local setups and PNG processing problems.


# What I am Doing Now:

- **Integrating LLM (SDC)**: Working on the integration of a suitable LLM from the **Siemens Digital Cloud (SDC)** for programmatic access. This involves:
    
    - Setting up access to the SDC-hosted LLM.
        
    - Integrating the API into the iPID application.
        
    - Designing and executing experiments to evaluate how well the LLM understands and classifies P&ID symbols using visual info and tags.
        
- **Supporting the Team**: Assisting with general Backend/Frontend tasks and helping Luca with the broader LLM Framework integration.
- **Refactoring & Cleanup**: Using the planning session to address technical debt in the UI by removing **dead code**, cleaning up the **Canvas service**, and deleting **commented-out code**.
