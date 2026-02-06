## Incident
Application logs not found in Linux log paths

## Commands run
sudo docker ps
curl http://localhost
curl http://localhost
curl http://localhost
ls /var/log
ls /var/log/nginx
sudo docker logs 9409722f30b1

## Output / signal
No nginx access logs found in /var/log
Container was running and responding to requests
Logs visible only via docker logs

## Action taken
Used docker logs to view container output

## Result
Nginx access logs visible from container

## Time to fix
~8 minutes
