# php_bianyi

PHP for MAC 编译选项及注意事项

#!/bin/bash

./configure --prefix=/usr/local/php --with-curl --with-freetype-dir --with-gd --with-gettext=/usr/local/opt/gettext \
  --with-kerberos --with-libdir=lib \
 --with-mysqli --with-openssl --with-pcre-regex --with-pdo-mysql --with-pdo-sqlite --with-pear --with-png-dir=/usr/local/opt/libpng --with-jpeg-dir=/usr/local/opt/libjpeg \
  --with-xmlrpc --enable-cgi \
  --with-xsl --with-bz2 --with-mhash --enable-fpm --enable-bcmath --enable-inline-optimization --enable-gd-native-ttf \
  --enable-mbregex --enable-mbstring --enable-opcache --enable-pcntl --enable-shmop --enable-soap --enable-sockets --enable-sysvsem \
  --enable-system --enable-libxml --with-libxml-dir=/usr/local/opt/libxml2 --enable-debug
  
  需要先安装如下组件
  
  brew install gettext
  
  cp -R /usr/local/opt/gettext/include/ /usr/local/include/
  
  cp -R /usr/local/opt/gettext/lib/ /usr/local/lib/
  
  brew install libpng
  
  brew install libjpeg
  
  brew install libxml2
  
  然后拷贝上面的几个库到/usr/local/include/ 及 /usr/local/lib/
  
  cp -R /usr/local/opt/libpng/include/ /usr/local/include/
  
  cp -R /usr/local/opt/libpng/lib/ /usr/local/lib/
  
  cp -R /usr/local/opt/libjpeg/include/ /usr/local/include/
  
  cp -R /usr/local/opt/libjpeg/lib/ /usr/local/lib/
  
  cp -R /usr/local/opt/libxml2/include/ /usr/local/include/
  
  cp -R /usr/local/opt/libxml2/lib/ /usr/local/lib/
  
  make
  
  make install
  
  这里没有安装curl，神烦，需要安装的到源码目录下的ext 通过phpize安装。
