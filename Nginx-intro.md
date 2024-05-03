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

### Proxy 
> In computer networking , a proxy server is a server application that acts as intermediary between a client requesting a resource and the server providing that resource.
> Client <-> proxy <-> Server
> 2 type
  1. Forward Proxy (if proxy from client side it's called forward proxy)
  2. Reverse Proxy (if proxy from Server side it's called reverse proxy)

### Reverse Proxy
> A proxy service which takes a client request, Passes it on to one or more servers.
> Proxying is typically used to distribute the load among several servers.
> seamlessly show content from different websites.
> or pass requests for processing to application server over protocolss other than HTTP.  

```
 loaction / {
    proxy_pass http:127.0.0.1:8080/;
 }
```
 > for trobleshooting
 - /var/log/nginx/
 - sudo cat /var/log/audit/audit.log | grep nginx | grep denied

 on Apache server :
 - List of all the httpd SELinux boolean
 command : getsebool -a | grep https

 - Enable the network connect boolean
 command : setsebool httpd_can_network_connect on -P