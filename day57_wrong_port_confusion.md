## Incident: Browser Showing Old Version After Deployment

### Signal
New version deployed on port 8081.
Curl showed updated content.
Browser initially showed old Nginx page.

### Actions Performed
Created new.html with updated content.

Stopped previous container:
sudo docker stop new-version
sudo docker rm new-version

Deployed new container with volume:
sudo docker run -d --name new-version -p 8081:80 -v $(pwd)/new.html:/usr/share/nginx/html/index.html nginx

Tested locally:
curl http://localhost:8081
→ New Production Version

Tested via browser:
http://18.219.81.119:8081/
→ Old Nginx page

Performed hard refresh (Ctrl + Shift + R).

Retested browser.
→ New Production Version displayed.

### Observations
Server was serving correct updated content.
Browser was caching previous response.

### Root Cause
Client-side browser cache.

### Learning
If curl shows new version but browser shows old:
Perform hard refresh or check cache.

### Incident Time
~5 minutes


