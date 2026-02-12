## Incident: Service Reachability Verification

### Signal
Testing access before and after stopping container.

### Actions Performed
Started nginx container:
sudo docker run -d --name my-nginx -p 8080:80 nginx

Verified running state:
sudo docker ps

Tested access:
curl http://localhost:8080

Stopped container:
sudo docker stop my-nginx

Tested access again:
curl http://localhost:8080

### Observations
Container state before stop: Up
Browser before stop: "Welcome to nginx!" page displayed
Browser after stop: Connection refused

### Root Cause
No issue. This was controlled service lifecycle testing.

### Learning
If container is running and port mapped → service reachable.
If container is stopped → connection refused.

### Incident Time
~5 minutes

