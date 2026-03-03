---
tags:
  - project
  - agile
  - sprint-review
  - planning
---
Last but not least, I’d like to tell you about one more improvement—both on the backend side and, as a result of that change, also in the UI.

To give you the full picture: before we perform any symbol, text, or line recognition, we run several image-processing functions. In some cases, these operations can take quite a long time. While they were running, the API was blocking any incoming requests, which was obviously not ideal.

During this sprint, we spent some time separating these image-processing steps into their own dedicated task. This means the API is no longer blocked, and the overall processing pipeline has become much more manageable and robust for future functions we add.

---

This was primarily a backend change, but in coordination with Anna, we also adjusted the UI to make this task visible there as well.

Oh and the api sonarcube gate also passed and there are mainly maintainability issues open

I think I’m the last one onspeaking, so unless anyone else wants to add something or has a question, we’re done.  
Thank you.