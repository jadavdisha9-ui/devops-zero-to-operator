## Incident: Port Conflict During Deployment

### Signal
Attempted to start a new container on port 8080
while an existing container was already using that port.

### Actions Performed
Verified running container:
sudo docker ps
→ static-test running on 8080

Attempted new deployment:
sudo docker run -d --name conflict-test -p 8080:80 nginx

### Observations
Docker returned error:
"Bind for 0.0.0.0:8080 failed: port is already allocated"

New container could not start.

### Root Cause
Port 8080 already in use by existing container (static-test).
Two containers cannot bind to same host port simultaneously.

### Learning
Before deploying new version:
Stop or remove old container using the same port.

### Incident Time
~5 minutes



