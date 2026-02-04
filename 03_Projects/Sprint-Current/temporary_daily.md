---
tags:
  - project
  - daily
  - scratchpad
---
**Data Analytics**

**Backend**

- Unsere Datenbank speichert fehlgeschlagene Statuswerte jetzt korrekt – das war vorher noch nicht sauber umgesetzt.
    
- Aktuell bauen wir ein vernünftiges Logging für das Backend-for-Frontend auf. Bisher hatten wir ein umfassendes Logging nur in der Core-API.
    
- Für alle AWS-Umgebungen gibt es jetzt ein Celery-Dashboard, womit sich Tasks deutlich einfacher debuggen lassen.
    
- Außerdem optimieren wir gerade Celery, insbesondere Concurrency und Prefetch-Multiplier, um die Task-Verarbeitung stabiler und robuster zu machen.
    
- Es gibt ein neues `image_processing`-Task, das zeitintensive Funktionen in einen separaten Celery-Worker auslagert.
    

**UI**

- Alle „Critical“ und „Major“ SonarQube-Findings in der UI wurden behoben.