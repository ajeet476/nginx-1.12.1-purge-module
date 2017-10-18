
## download purge module
```shell

cd /tmp/
# purge module
wget http://labs.frickle.com/files/ngx_cache_purge-2.3.tar.gz
tar -xzvf ngx_cache_purge-2.3.tar.gz
```

# edit config file

 [Reference](./config)



##  download nginx source
wget http://nginx.org/download/nginx-1.12.1.tar.gz
tar -xzvf nginx-1.12.1.tar.gz
cd /tmp/nginx-1.12.1



### command to make dynamic module

```shell
./configure --add-dynamic-module=/tmp/ngx_cache_purge-2.3 \
     --prefix=/etc/nginx \
     --sbin-path=/usr/sbin/nginx \
     --modules-path=/usr/lib64/nginx/modules \
     --conf-path=/etc/nginx/nginx.conf \
     --error-log-path=/var/log/nginx/error.log \
     --http-log-path=/var/log/nginx/access.log \
     --pid-path=/var/run/nginx.pid \
     --lock-path=/var/run/nginx.lock \
     --http-client-body-temp-path=/var/cache/nginx/client_temp \
     --http-proxy-temp-path=/var/cache/nginx/proxy_temp \
     --http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp \
     --http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp \
     --http-scgi-temp-path=/var/cache/nginx/scgi_temp \
     --user=nginx \
     --group=nginx\
     --with-compat\
     --with-file-aio\
     --with-threads \
     --with-http_addition_module \
     --with-http_auth_request_module \
     --with-http_dav_module \
     --with-http_flv_module \
     --with-http_gunzip_module \
     --with-http_gzip_static_module \
     --with-http_mp4_module \
     --with-http_random_index_module \
     --with-http_realip_module \
     --with-http_secure_link_module \
     --with-http_slice_module \
     --with-http_ssl_module \
     --with-http_stub_status_module \
     --with-http_sub_module \
     --with-http_v2_module \
     --with-mail --with-mail_ssl_module --with-stream --with-stream_realip_module --with-stream_ssl_module \
     --with-stream_ssl_preread_module \
     --with-cc-opt='-O2 -g -pipe -Wall -Wp,-D_FORTIFY_SOURCE=2 -fexceptions -fstack-protector-strong --param=ssp-buffer-size=4 -grecord-gcc-switches -m64 -mtune=generic -fPIC' --with-ld-opt='-Wl,-z,relro -Wl,-z,now -pie'
```

### make modules

```shell
$  make modules
```



