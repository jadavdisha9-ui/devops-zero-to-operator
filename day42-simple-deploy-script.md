## Incident
Manual deployment caused confusion and inconsistent results

## Commands run
nano index.html
nano deploy.sh
chmod +x deploy.sh
./deploy.sh
curl http://localhost:8080

## Output / signal
Application showed broken HTML when bad content was deployed
Deploy script executed successfully but deployed incorrect content

## Action taken
Fixed source index.html
Re-ran deploy script to copy corrected file

## Result
Application restored to correct state
Deployment became repeatable via script

## Time to fix
~15 minutes
