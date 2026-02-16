## Incident: Website Not Reachable

### Initial State
Container deployed:
sudo docker run -d --name final-app -p 8080:80 nginx

Service working:
curl http://localhost:8080

### Failure Observed
Container manually stopped:
sudo docker stop final-app

Website not reachable:
curl http://localhost:8080 → Connection refused

### Diagnosis Steps
Checked running containers:
sudo docker ps

Observation:
No container running.

### Fix Performed
Started container:
sudo docker start final-app

Verified container:
sudo docker ps

Tested service:
curl http://localhost:8080

### Final State
Service restored.
Container running.

### Incident Time
~3 minutes


