### lxc container:
+----------+---------+---------------------+------+------------+-----------+
|   NAME   |  STATE  |        IPV4         | IPV6 |    TYPE    | SNAPSHOTS |
+----------+---------+---------------------+------+------------+-----------+
| proxy    | RUNNING | 192.168.0.2 (eth0)  |      | PERSISTENT | 0         |
+----------+---------+---------------------+------+------------+-----------+

### In lxc proxy Nginx main Config:

vim /etc/nginx/nginx.conf

```
user   www-data;
worker_processes  auto;

error_log  /var/log/nginx/error.log info;
pid        /var/run/nginx.pid;

events {
    worker_connections  1024;
}

http {

  include       mime.types;
  default_type  application/octet-stream;

  # connection limit zones
  limit_conn_zone $server_name zone=dvsconn:10m;
  # rate limit zones
  limit_req_zone $binary_remote_addr zone=ip:10m rate=4r/m;
  limit_req_zone $server_name zone=all:10m rate=20r/m;

  # performance log format
  log_format performance '$remote_addr\t[$time_local]\t-\t$remote_user\t'
    '"$request"\t$status\t$body_bytes_sent\t'
    '"$http_referer"\t"$http_user_agent"\t'
    '$upstream_response_time';

  index  index.html index.htm;

  # Include separate files in the main "http{}" configuration
  include  conf.d/*.conf;
  
    # Allow status requests from localhost
  server
  {
    listen 127.0.0.1;
    server_name localhost;

    access_log /var/log/nginx/perf.log performance;

    location /nginx_status {
      stub_status on; # activate stub_status module
      access_log off;
      allow 127.0.0.1; # localhost
      allow ::1; # localhost
      deny all;
    }
  }

  # Redirect http to https
  server {
    listen 80 ;
    server_name mis.nmcpye.org;
    return 301 https://$host$request_uri;
  }

  # Main server block
  server {
    listen 443 ssl http2;
    server_name  mis.nmcpye.org;
	# Includes for the default hostname
    include  default.d/*.conf;

    include upstream/*.conf;
  }

}
```
### In lxc proxy Nginx main Config:

vim /etc/nginx/upstream/pgadmin.conf

```
    # Proxy pass to servlet container

    location /pgadmin4 {
      proxy_pass                http://192.168.0.40/pgadmin4;
      # proxy_redirect            off;
      proxy_set_header Host $host;
      proxy_set_header X-Real-IP $remote_addr;
      #proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header X-Forwarded-For $remote_addr;
      proxy_redirect http:// https://;
      proxy_set_header X-Forwarded-Proto  https;

      proxy_connect_timeout  480s;
      proxy_read_timeout     480s;
      proxy_send_timeout     480s;

      proxy_buffer_size        128k;
      proxy_buffers            8 128k;
      proxy_busy_buffers_size  256k;
   }
   #if ($http_origin = ''){
   #  set $http_origin "*";
   #}
   #proxy_hide_header Access-Control-Allow-Origin;
   #add_header Access-Control-Allow-Origin $http_origin;

   add_header X-Frame-Options DENY;
   add_header 'Access-Control-Allow-Credentials' 'true';
   add_header 'Access-Control-Allow-Headers' 'Authorization,Accept,Origin,DNT,X-CustomHeader,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Content-Range,Range';
   add_header 'Access-Control-Allow-Methods' 'GET,POST,OPTIONS,PUT,DELETE,PATCH';
   add_header 'Access-Control-Max-Age' 1728000;
```
