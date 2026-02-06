## Incident
Application became unreachable after container stopped

## Commands run
sudo docker ps
sudo docker stop 9409722f30b1
curl http://localhost
sudo docker ps
sudo docker ps -a
sudo docker start 9409722f30b1
curl http://localhost

## Output / signal
Application responded when container was running  
Connection refused after container stopped  
docker ps showed no running containers  
docker ps -a showed container in Exited state

## Action taken
Restarted stopped container using docker start

## Result
Application accessible again and nginx page loaded

## Time to fix
~5 minutes
