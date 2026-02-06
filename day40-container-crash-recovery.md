## Incident
Application went down after container crash and required recovery

## Commands run
sudo docker ps
sudo docker kill e83ba3a19de9
sudo docker ps
curl http://localhost
sudo docker ps
sudo docker start e83ba3a19de9
curl http://localhost

## Output / signal
Container stopped after kill command
Application unreachable (connection refused)
Container not running initially

## Action taken
Waited for auto-recovery attempt
Manually started container

## Result
Container running again
Application accessible via browser

## Time to fix
~10 minutes




