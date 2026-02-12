## Incident: Application unreachable after successful CI/CD deploy

### Signal
Application not accessible in browser.
Log showed:
open() "/usr/share/nginx/html/login" failed (No such file or directory)

### Investigation
Checked container state using:
docker ps -a

Read container logs using:
docker logs b6b22dd13f3e

Checked exit code using:
docker inspect b6b22dd13f3e --format='{{.State.ExitCode}}'

### Findings
Container exit code: 0
Container did not crash.
Nginx attempted to access a file path that does not exist.

### Root Cause
Request was made to /login but no corresponding file existed in nginx static directory.

### Action Taken
No restart performed.
No redeploy performed.
Identified issue as application-level routing/file issue.

### Result
Confirmed infrastructure layer was healthy.
Issue isolated to application path handling.

### Prevention
Ensure correct file structure or configure proper route handling before deployment.

## Time taken
5 minutes
