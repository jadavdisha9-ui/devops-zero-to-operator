## Incident: Proper Redeploy Sequence

### Signal
Previous deployment caused port conflict.
Required clean redeploy process.

### Actions Performed
Checked running container:
sudo docker ps

Stopped old container:
sudo docker stop static-test

Removed old container:
sudo docker rm static-test

Deployed fresh container:
sudo docker run -d --name clean-deploy -p 8080:80 nginx

Tested service:
curl http://localhost:8080

### Observations
Container state: Running
Curl output: Nginx welcome page displayed successfully

### Root Cause
No issue. Controlled redeploy sequence executed properly.

### Learning
Correct redeploy pattern:
Stop → Remove → Run
Prevents port conflicts during deployment.

### Incident Time
~5 minutes


