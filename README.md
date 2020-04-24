# Nginx-SSL-setting-
server {
        listen 443;
        server_name bqscorekeeper.com;


        root /user/share/nginx/html;
        index index.html index.htm;

        ssl on;
        ssl_certificate /root/bqscorekeeper.com.crt;
        ssl_certificate_key /root/bqscorekeeper.com.key;

        ssl_protocols SSLv3 TLSv1 TLSv1.1 TLSv1.2;
        ssl_prefer_server_ciphers on;
        ssl_ciphers 'EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH';
        location / {
                try_files $uri $uri/ =404;
