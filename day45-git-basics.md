## Incident
Manual rollback was unreliable and required a proper version control system

## Commands run
git init
git status
nano index.html
git add index.html
git commit -m "Initial working version"
nano index.html
curl http://localhost:8080
git status
git checkout -- index.html
curl http://localhost:8080

## Output / signal
Application broke after bad change
Git detected modified file
Rollback restored correct output immediately

## Action taken
Used Git to revert file to last committed state

## Result
Application restored to known-good version reliably

## Time to fix
~10 minutes




