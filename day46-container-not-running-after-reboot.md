## Incident
Application stopped responding after server reboot.

## Commands run
curl http://localhost:8080

## sudo reboot
ssh -i ~/devops-key.pem ubuntu@18.219.81.119
docker ps
docker ps -a
docker start <container_id>
curl http://localhost:8080

## Output / signal
Application worked before reboot
After reboot, connection refused
docker ps showed no running containers
docker ps -a showed container in Exited state

## Action taken
Identified container was not running after reboot
Started container manually using docker start

## Result
Application restored successfully after container restart

## Time to fix
10–15 minutes
