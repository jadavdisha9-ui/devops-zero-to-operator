## Incident: Service Under CPU Stress

### Signal
High CPU usage observed while service running.

### Actions Performed
Deployed nginx:
sudo docker run -d --name prod-nginx -p 8080:80 nginx

Generated CPU load:
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &

Observed system:
top

Identified high CPU processes:
PID 78338 → 73.8% CPU
PID 78337 → 67.2% CPU
PID 78336 → 58.3% CPU

Stopped processes:
kill 78338
kill 78337
kill 78336

Rechecked system:
top

### Observations
CPU during load:
%Cpu(s): 58.2 us, 41.8 sy, 0.0 id  →  ~100% busy

After kill:
%Cpu(s): 0.0 us, 0.2 sy, 99.7 id  →  CPU returned to idle

Memory remained stable.
Service (curl / browser) continued responding.

### Root Cause
Artificial CPU overload from multiple background processes.

### Learning
If CPU is high:
1. Use top
2. Identify highest %CPU process
3. Kill problematic PID
4. Verify CPU returns to idle
5. Confirm service health

### Incident Time
~8 minutes
