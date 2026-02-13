## Incident: High CPU Simulation and Diagnosis

### Signal
Simulated artificial CPU spike using background process.

### Actions Performed
Started CPU load:
yes > /dev/null &

Observed system:
top

Identified high CPU process:
PID 77344 (yes) using ~99% CPU

Confirmed process:
ps aux | grep yes

Stopped process:
kill 77344

Rechecked system:
top

### Observations
CPU during load:
~99% usage by 'yes' process

Top process:
yes (PID 77344)

CPU after kill:
Returned to ~100% idle

### Root Cause
Artificial CPU load generated intentionally.
System functioning normally after process termination.

### Learning
If CPU spikes:
1. Use top
2. Identify high %CPU process
3. Find PID
4. Kill if necessary

### Incident Time
~10 minutes




