## Incident
Application down after server reboot because container did not auto-start

## Commands run
sudo reboot
sudo docker ps
sudo docker ps -a
curl http://localhost
sudo systemctl status nginx
sudo systemctl stop nginx
sudo docker start 9409722f30b1
curl http://localhost

## Output / signal
Application unreachable after reboot
docker ps showed no running containers
docker ps -a showed container in Exited state
Docker start failed due to port 80 already in use
Linux nginx service was running and holding port 80

## Action taken
Stopped Linux nginx service
Started Docker nginx container manually

## Result
Docker container running
Application accessible again via browser

## Time to fix
~15 minutes

## Time to fix
~15 minutes
