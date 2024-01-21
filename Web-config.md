# How to config web file in conf.d directory

- name and command
  > path : cd /etc/nginx/conf.d <br>
  > sudo vim web.conf

### Server Block in web.conf
```
server {
        listen 80 default_server ;
        root /var/www/yoga ;

        server_name _;

        index index.html index.htm ;

        location / {
                try_files $uri $uri/ = 404;

        }
}
```
### Authentication usage
- created Dev Environment with authentication , only allow authorized users only
  ```
  create file hpasswd file for username and password
  > sudo sh -c "echo -n 'admin:' >> /etc/nginx/.htpasswd"
  generate password :
  > sudo sh -c "openssl passwd -apr1 >> /etc/nginx/.htpasswd"
  ```
  add auth in server block
  ```
  server {

  listen 80 default_server;
  root /var/www;

  server_name _;
  auth_basic "Under dev portal" ;
  auth_basic_user_file /etc/nginx/.htpasswd;


  index index.html index.htm;

  location / {
        auth_basic off ;
        try_files $uri $uri/ =404;
  }

   location /dev {    
        try_files $uri $uri/ =404;

  }
  }
  ```
### Add Self Signed SSL certificate :
- Command
  > sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/selfsigned.key -out /etc/nginx/selfsigned.crt
- Add these certificate in server block
  ```
  listen 443 ssl;
    server_name _;

    ssl_certificate /etc/nginx/selfsigned.crt ;
    ssl_certificate_key /etc/nginx/selfsigned.key;
  ```
- sudo nginx -T -> for all configuaration files
