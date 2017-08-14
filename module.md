sudo apt-get update;
sudo apt-get install -y build-essential git libpcre3 libpcre3-dev openssl libssl-dev zlibc zlib1g zlib1g-dev
cd $HOME &amp;&amp; cd nginx-*
./configure --prefix=/etc/nginx \
--sbin-path=/usr/sbin/nginx \
--conf-path=/etc/nginx/nginx.conf \
--pid-path=/var/run/nginx.pid \
--lock-path=/var/run/nginx.lock \
--with-http_ssl_module \
--with-http_realip_module \
--with-http_addition_module \
--with-http_sub_module \
--with-http_dav_module \
--with-http_flv_module \
--with-http_mp4_module \
--with-http_gunzip_module \
--with-http_gzip_static_module \
--with-http_random_index_module \
--with-http_secure_link_module \
--with-http_stub_status_module \
--with-file-aio \
--with-pcre \
--with-file-aio \
--with-cc-opt='-g -O2 -fstack-protector --param=ssp-buffer-size=4 -Wformat -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -DTCP_FASTOPEN=23' \
--with-ld-opt='-Wl,-z,relro -Wl,--as-needed -L /usr/lib' \
--with-ipv6 \
--with-debug \
--without-http_scgi_module \
--without-http_uwsgi_module \
--add-module=$HOME/nginx-rtmp-module
make
sudo make install
