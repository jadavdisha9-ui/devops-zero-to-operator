# Incident:
Website served default page after config change

# What broke:
Expected index file not loading

# Commands I used:
sudo nano /etc/nginx/sites-available/default
sudo nginx -t
sudo systemctl reload nginx
sudo rm /var/www/html/index.nginx-debian.html

# Error seen:
Site did not change / 404 after fix

# How I fixed:
Removed fallback index file

# Time to fix:
20 minutes
