## UI

Siemens Software Analytics: 

Anna KPIs: 

- how many user per tenant access the iPID application
- how many tenant are active (active user) at the same time?
- how many documents one tenant processes (file upload and download) for certain time e.g. per month?
- how many documents one user processes  (file upload and download) for certain time e.g. per day?
- how many files are getting processed in a time frame e.g. working day. how is the distribution of the upload time point over this time period?
- how much time it takes from upload to download (validation). how long the uploaded files are stored in the application before download
- how long the user needs for symbol/lines/text validation?
- how long the AI processing takes per file. consider file size and other file parameter in the same monitoring step
- how many files cannot be processed because of error (rollback)?
- how often (ratio uploaded files/rollbacked files) the user initiates rollback because of unsufficient quality?
- waiting times in the queue by missing paralel file processing
- how many symbols/texts/lines are getting adapted manually?
- how many symbols/texts/lines/ need to be added manually? ratio recognized/unrecognized symbols/texts/lines.
- how many symbols/texts/lines are getting rejected? how was the confidence? which symbol type was initially recognized and how it was changed.

## API

Database: 

- User IDs 
- Fetch User Names and Map them to the User IDs before returning the jobs page 


## BFF

