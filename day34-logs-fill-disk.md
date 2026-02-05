## Incident
Log file growth filled disk and blocked writes

## Commands run
cd /var/log
sudo touch app.log
sudo chmod 666 app.log
yes "ERROR something failed" | sudo tee -a /var/log/app.log > /dev/null
df -h
sudo du -sh /var/log/*
sudo truncate -s 0 /var/log/app.log
df -h

## Output / signal
tee error: No space left on device  
Root filesystem reached 100% usage  
app.log size ~4.9G

## Action taken
Truncated app.log to zero size

## Result
Disk usage dropped to ~36%  
System write capability restored
## Time to fix
~10 minutes
