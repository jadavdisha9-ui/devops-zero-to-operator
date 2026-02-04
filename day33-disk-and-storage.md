## Incident
Disk usage spike

## Commands run
df -h
sudo du -sh /tmp/*
touch /tmp/testfile
sudo rm /tmp/bigfile.log

## Output / signal
Root filesystem at 92%
File creation delayed

## Action taken
Removed large file in /tmp

## Result
Disk usage dropped to 38%

## Time to fix
6 minutes
