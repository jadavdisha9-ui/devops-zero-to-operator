## Incident
Docker container running but application unreachable

## Commands run
sudo docker run -d nginx
sudo docker ps
curl http://localhost
sudo docker stop c84f156470e8
sudo docker rm c84f156470e8
sudo systemctl stop nginx
sudo docker run -d -p 80:80 nginx
curl http://localhost

## Output / signal
Container running without port mapping  
Port 80 already in use by Linux nginx  
Application not accessible initially

## Action taken
Stopped Linux nginx  
Restarted container with port mapping

## Result
Application accessible via browser

## Time to fix
~15 minutes
## Time to fix
~15 minutes
