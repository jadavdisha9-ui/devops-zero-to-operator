## Incident: Container Restart Loop

### Signal
Container never becomes stable.
Status shows: Restarting (1)

### Actions Performed
Checked existing containers:
sudo docker ps -a

Removed running container:
sudo docker rm -f app-v1

Started failing container:
sudo docker run -d --name bad-app --restart always nginx sh -c "exit 1"

Checked running containers:
sudo docker ps

Checked logs:
sudo docker logs bad-app

Checked container status again:
sudo docker ps -a

### Observations
Container state:
Restarting (1)

Logs output:
No logs shown

Behavior:
Container exits immediately and Docker restarts it continuously.

### Root Cause
Container command exits instantly ("exit 1").
Restart policy set to always.
Docker keeps restarting it.

### Learning
If container shows:
Restarting (1)

Check:
1. Command being executed
2. Restart policy
3. Exit behavior

Container may not be broken —
It may be configured to restart endlessly.

### Incident Time
~5 minutes


