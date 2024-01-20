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
sudo nginx -T -> for all configuaration files
