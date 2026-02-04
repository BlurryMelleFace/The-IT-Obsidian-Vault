---
tags:
  - project
  - daily
  - scratchpad
---
Yesterday, I worked on adjusting the UI to align with the backend changes I made. As I explained yesterday, we are now persisting the `file_processing` task in the database together with its proper status. With this change, the UI can access this data when fetching jobs.

As of yesterday, 4 out of the now 5 tasks are being displayed. This means we can now also track longer-running file-processing tasks, such as redlining, without the user having to wonder what happened to their file.

Rahul reviewed the functionality and the tests, after which I merged the changes and promoted them to QA.



Data Analytics: 

Backend
git 
Unsere Datenbank persistiert nun fehlgeschlagene Statuswerte korrekt; dies fehlte zuvor.

Wir arbeiten an der Implementierung eines ordnungsgemäßen Loggings für das Backend-for-Frontend, da wir bisher nur in der Core-API über ein umfassendes Logging verfügen.

Wir haben jetzt ein Celery-Dashboard für alle AWS-Umgebungen, wodurch wir Tasks effizienter debuggen können.

Wir optimieren derzeit Celery (Anpassung von Concurrency und Prefetch-Multipliers, um unsere Task-Verarbeitung robuster zu machen).

UI

Alle "Critical" und "Major" SonarQube-Findings wurden in der UI behoben.

