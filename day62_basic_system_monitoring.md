## Incident: Basic System Health Observation

### Signal
Checking system resource usage manually.

### Actions Performed
Checked CPU and memory:
top

Checked memory breakdown:
free -m

Checked disk usage:
df -h

### Observations
CPU:
~99% idle (system mostly free)

Memory:
Total: 914 MB
Used: 249 MB
Free: 112 MB
Available: 487 MB

Disk:
Root disk 7.6G total
3.2G used
4.5G available
42% usage

### Root Cause
No issue. System is healthy.

### Learning
Basic monitoring commands:
- top → CPU & processes
- free → memory
- df → disk

These are first checks during “server slow” incidents.

### Incident Time
~5 minutes




