## Incident
System freeze during load

## Commands run
stress --cpu 2 --vm 1 --vm-bytes 300M --timeout 300
ps aux | grep stress

## Output / signal
Only grep process present

## Action taken
None (stress already stopped)

## Result
System responsive

## Time to fix
15 minutes
