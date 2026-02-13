## Incident: Container With Restart Policy

### Signal
Container configured with --restart always.
Expected restart behavior.

### Actions Performed
Removed old containers for clean state.

Started container:
sudo docker run -d --name auto-test --restart always -p 8080:80 nginx

Stopped container manually:
sudo docker stop auto-test

Checked container state:
sudo docker ps
sudo docker ps -a

### Observations
After stop: Container stopped.
After waiting: Container remained stopped.
No automatic restart triggered.

### Root Cause
Manual stop does not immediately trigger restart policy.

### Learning
--restart always works on crash or daemon restart.
Stopped containers remain in system until removed.

### Incident Time
~5 minutes


