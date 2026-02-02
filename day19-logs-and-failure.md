# Day 19 — Logs and Failure

## What I broke
I added a wrong line in the nginx configuration file on my EC2 server.

## What failed
Nginx service did not start after restarting.

## Which log showed the problem
The nginx error log showed the exact reason for the failure.

## How I fixed it
I removed the wrong line from the config and restarted nginx.
