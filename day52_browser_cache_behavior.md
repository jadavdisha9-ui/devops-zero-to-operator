## Incident: Update File While Container Running

### Signal
Updated local index.html while container was already running.
Expected new version to be served.

### Actions Performed
Verified container running:
sudo docker ps

Updated file:
nano index.html
Changed content to:
<h1>Version 3</h1>

Tested locally:
curl http://localhost:8080

Tested from browser:
http://18.219.81.119:8080/

### Observations
Curl output: Version 3
Browser output: Version 3
Container continued running without restart.

### Root Cause
No issue. Volume mount allows live file updates without restarting container.

### Learning
When using volume mount:
File changes reflect immediately.
Container restart not required.

### Incident Time
~5 minutes



