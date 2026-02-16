## Incident: Container Running But Content Updated

### Signal
Container running and reachable.
File content changed on host.

### Actions Performed
Created Version 1:
echo "Version 1" > index.html

Started container with volume mount:
sudo docker run -d --name app-v1 -p 8080:80 -v $(pwd)/index.html:/usr/share/nginx/html/index.html nginx

Tested:
curl http://localhost:8080

Updated file:
echo "Version 2" > index.html

Tested again:
curl http://localhost:8080

### Observations
Initial output:
Version 1

After change:
Version 2

Container state:
Running

### Root Cause
File was mounted from host.
Changes on host reflected immediately in container.

### Learning
If container uses volume mount:
File changes apply instantly.
No container restart needed.

### Incident Time
~5 minutes



