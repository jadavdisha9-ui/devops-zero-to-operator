## Incident: Disk Usage Simulation

### Signal
Simulated disk usage increase to observe behavior.

### Actions Performed
Checked disk usage:
df -h

Created 1GB file:
fallocate -l 1G bigfile

Checked disk again:
df -h

Removed file:
rm bigfile

Checked disk again:
df -h

### Observations
Disk before:
Used: 3.2G
Available: 4.5G
Usage: 42%

Disk during:
Used: 4.2G
Available: 3.5G
Usage: 55%

Disk after:
Used: 3.2G
Available: 4.5G
Usage: 42%

### Root Cause
Artificial file creation increased disk usage.
Removing file restored disk capacity.

### Learning
If disk usage increases:
1. Use df -h to check usage
2. Identify large files
3. Remove unnecessary files

### Incident Time
~5 minutes


