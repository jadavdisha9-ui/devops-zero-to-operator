## Incident: Multiple Containers Serving Different Ports

### Signal
Deployed new container without stopping old one.

### Actions Performed
Verified existing container:
sudo docker ps
→ clean-deploy running on 8080

Started new container:
sudo docker run -d --name new-version -p 8081:80 nginx

Tested both ports:
curl http://localhost:8080
curl http://localhost:8081

### Observations
Port 8080: Nginx page displayed (old container)
Port 8081: Nginx page displayed (new container)
Both services running simultaneously.

### Root Cause
Old container was not stopped before new deployment.
Two containers serving on different ports.

### Learning
Deployment does not automatically replace old service.
If old container not stopped, it continues serving traffic.

### Incident Time
~5 minutes


