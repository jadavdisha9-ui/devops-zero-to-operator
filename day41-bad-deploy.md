## Incident
Bad application change caused web page to break

## Commands run
nano index.html
curl http://localhost:8080
nano index.html
curl http://localhost:8080

## Output / signal
Application returned broken / empty response after bad change
Application returned expected output after rollback

## Action taken
Reverted index.html to last working version

## Result
Application restored successfully

## Time to fix
~5 minutes
