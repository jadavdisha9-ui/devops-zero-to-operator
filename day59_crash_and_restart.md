## Incident: Container Crash With Restart Policy

### Signal
Container configured with --restart always.
Container intentionally forced to exit with failure.

### Actions Performed
Cleaned old containers:
sudo docker rm $(sudo docker ps -aq)

Started crash container:
sudo docker run -d --name crash-test --restart always nginx sh -c "exit 1"

Observed container state:
sudo docker ps
sudo docker ps -a

### Observations
Container status:
Restarting (1)

Container repeatedly restarting automatically.

### Root Cause
Container exited with status 1 (failure).
Restart policy (--restart always) triggered automatic restart.

### Learning
Restart policy activates when:
- Container crashes
- Not when manually stopped

Restart loop visible as:
Restarting (1) state in docker ps.

### Incident Time
~5 minutes




