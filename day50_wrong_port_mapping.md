## Incident: Service Running but Not Reachable Externally

### Signal
Container running successfully.
Local curl worked on port 8081.
Public IP access failed.

### Actions Performed
Started container:
sudo docker run -d --name port-test -p 8081:80 nginx

Verified container:
sudo docker ps

Tested wrong port:
curl http://localhost:8080
→ Connection refused

Tested correct port locally:
curl http://localhost:8081
→ Nginx page displayed

Tested public access:
http://18.219.81.119:8081/
→ Not reachable

Checked EC2 Security Group inbound rules.
Added rule:
Custom TCP
Port: 8081
Source: Anywhere (IPv4)

Retested public access.
→ Successful

### Observations
Container state: Running
Port mapping: 8081 -> 80
Local access: Working
Public access before rule: Blocked
Public access after rule: Working

### Root Cause
Two-layer issue:
1. Initial test used wrong port (8080 instead of 8081).
2. EC2 Security Group did not allow inbound traffic on port 8081.

### Learning
If container runs but service not reachable:
1. Verify correct port mapping.
2. Verify cloud firewall (Security Group).

### Incident Time
~10 minutes



