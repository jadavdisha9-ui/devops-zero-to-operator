## Incident: High Memory Usage Simulation

### Signal
Artificial memory load created using Python.

### Actions Performed
Started memory allocation:
python3 -c "a = ' ' * 300000000; input()"

Checked memory:
free -m
top

Stopped process using Ctrl + C.

Checked memory again:
free -m

### Observations
Memory during load:
Used: 547 MB
Free: 65 MB

Top memory process:
Python process (temporary memory allocation)

Memory after stop:
Used: 281 MB
Free: 331 MB

### Root Cause
Intentional memory allocation for simulation.

### Learning
If memory increases:
1. Use free -m
2. Use top to identify process
3. Stop process if needed

### Incident Time
~5 minutes



