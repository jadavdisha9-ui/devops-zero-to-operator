## Incident
Application state was overwritten and correct version could not be reliably restored

## Commands run
nano index.html
curl http://localhost:8080
cp index.html index_v1.html
nano index.html
curl http://localhost:8080
cp index_v1.html index.html
curl http://localhost:8080

## Output / signal
Application continued showing broken output
Rollback did not restore expected content

## Action taken
Inspected backup file contents
Identified backup was created after bad change

## Result
Rollback mechanism worked, but restored an already broken version

## Time to fix
~15 minutes
