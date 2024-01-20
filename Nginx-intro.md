# Usage of Nginx
------------------------------
+ Web server
+ Gateway
+ Reverse Proxy
+ caching
+ Rate limit
+ Host static sites/multi sites
+ load balancer
------------------------------------------------------------------------------------
### Step to install NGINX on Linux
```
sudo apt-get update
sudo apt-get install nginx
sudo systemctl status nginx

--- for check nginx files ---
cd /etc/nginx
```
--------------------
## nginx.conf File
```
cd /etc/nginx/nginx.conf
```
### main part in conf file 
- Events block
  - worker-connections details

- http block (Mainly use)
  - logs 1.access_log /var/log/nginx/access.log; and 2. error_log /var/log/nginx/error.log; <br>
  - 2 location includes <br>
    - include /etc/nginx/conf.d/*.conf;
    - include /etc/nginx/sites-enabled/*;


---------------------
- Default HTML file for nginx
  > cd /var/www/html
---------------------
- check all configuration are valid or not
  > sudo nginx -t
- reload nginx
  > sudo systemctl reload nginx
