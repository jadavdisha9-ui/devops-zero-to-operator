## Incident: Container Stuck in Restart Loop

### Signal
Container showing status:
Restarting (1)

### Actions Performed
Checked running containers:
sudo docker ps

Checked logs:
sudo docker logs crash-test

Checked exit code:
sudo docker inspect crash-test --format='{{.State.ExitCode}}'

### Observations
Logs: No meaningful output (container exits immediately)
Exit code: 1
Container repeatedly restarting

### Root Cause
Container intentionally configured to exit with failure.
Restart policy (--restart always) causing continuous restart loop.

### Learning
If container shows "Restarting":
1. Check logs
2. Check exit code
3. Identify crash reason
Restart loop indicates failure, not success.

### Incident Time
~5 minutes


