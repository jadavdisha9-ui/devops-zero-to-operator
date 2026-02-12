## Incident: Website Not Reachable (Connection Refused)

### Signal
Browser showed:
Connection refused

### Actions Performed
Checked running containers:
sudo docker ps

Checked all containers:
sudo docker ps -a

Attempted to inspect container file:
sudo docker exec -it  fc43e1e8c840 cat /usr/share/nginx/html/index.html

Checked host file:
cat index.html

### Observations
Container state: Not running
Browser output: Connection refused
Container file access: Container is not running
Host file: index.html not found

### Root Cause
No container was running.
No service was listening on port 8080.

### Learning
Connection refused usually means:
Nothing is running on that port.

### Incident Time
~5 minutes
