# Incident Thinking: How I Approach a “Site Is Down” Problem

In DevOps, problems rarely fail in one place. Instead of guessing or restarting things blindly, 
I try to understand which layer of the system is actually broken.
When someone says “the site is down”, I try not to panic or restart things randomly.
I think in layers and check them one by one.

First, I check whether the server exists and has an IP address.
If the server itself is not alive, nothing else matters.

Second, I check reachability to see if I can reach the server at all.
If the network path is broken, the application cannot be accessed.

Third, I check DNS, which works like a phonebook.
If the name is not resolving correctly, the site can look down even when the server is working.

Fourth, I check ports and firewall rules.
Even if everything else is fine, closed doors can block access.

Finally, I check the service health.
I see whether the service is running and look at logs to understand what happened.

The order matters because checking the wrong layer wastes time.
Restarting services blindly does not fix network or DNS problems.

Instead of blind restarts, I try to understand which layer failed
and fix the actual cause of the problem.
