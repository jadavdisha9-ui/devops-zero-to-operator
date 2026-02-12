## Incident: Deploy New Version Using Volume Mount

### Signal
Deployed updated index.html.
Expected new version to be served.

### Actions Performed
Created new index.html with content:
<h1>Version 2</h1>

Stopped old container:
sudo docker stop port-test

Started new container with volume mount:
sudo docker run -d --name version-test -p 8080:80 -v $(pwd)/index.html:/usr/share/nginx/html/index.html nginx

Tested service:
curl http://localhost:8080

### Observations
Container state: Running
Browser output: Version 2 displayed
Deployment successful.

### Root Cause
No issue. Controlled version update using volume mount.

### Learning
Using volume mount allows serving local file directly inside container.
Stopping old container ensures correct service instance is running.

### Incident Time
~5 minutes



