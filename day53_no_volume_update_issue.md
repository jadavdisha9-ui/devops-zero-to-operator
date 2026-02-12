## Incident: File Updated But Container Not Reflecting Changes

### Signal
Local file modified.
Expected updated version to appear.
Output remained unchanged.

### Actions Performed
Stopped previous container:
sudo docker stop version-test

Started container without volume mount:
sudo docker run -d --name static-test -p 8080:80 nginx

Verified output:
curl http://localhost:8080
→ Welcome to nginx

Modified local file:
nano index.html
Changed to:
<h1>Version 4</h1>

Retested:
curl http://localhost:8080
→ Still Welcome to nginx

### Observations
Container running.
Local file updated.
Container output unchanged.

### Root Cause
Container not using local file.
No volume mount configured.

### Learning
Without volume mount:
Container serves its internal file.
Host file changes do not affect running container.

### Incident Time
~5 minutes



