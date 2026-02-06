## Incident
Docker container did not restart automatically after server reboot

## Commands run
sudo docker ps
sudo docker stop 9409722f30b1
sudo docker rm 9409722f30b1
sudo docker run -d --restart unless-stopped -p 80:80 nginx
sudo reboot
sudo docker ps
curl http://localhost

## Output / signal
After reboot, container started automatically
Application accessible without manual intervention

## Action taken
Ran container with restart policy enabled

## Result
Container auto-started after reboot
Application stayed available

## Time to fix
~10 minutes
