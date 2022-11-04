# install
## install from source
```
cd /usr/local/src/
```

### ubuntu
```
apt-get -y install wget
#apt-get -y install libcurl4-openssl-dev libjansson-dev libldap2-dev liblua5.4-dev libnghttp2-dev libxml2-dev
```

### fedora
```
dnf -y install wget
#dnf -y install libcurl-devel jansson-devel openldap-devel lua-devel libnghttp2-devel libxml2-devel
```

### opensuse
```
zypper --non-interactive install wget gzip
#zypper --non-interactive install libcurl-devel libjansson-devel openldap2-devel lua-devel libnghttp2-devel libxml2-devel
```

### download source
```
wget https://www.zlib.net/zlib-1.2.13.tar.gz
wget https://github.com/libexpat/libexpat/releases/download/R_2_5_0/expat-2.5.0.tar.gz
wget https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-3.6.1.tar.gz

wget https://dist.apache.org/repos/dist/release/apr/apr-1.7.0.tar.gz
wget https://dist.apache.org/repos/dist/release/apr/apr-util-1.6.1.tar.gz
wget https://github.com/PCRE2Project/pcre2/releases/download/pcre2-10.39/pcre2-10.39.tar.gz

wget https://dist.apache.org/repos/dist/release/httpd/httpd-2.4.54.tar.gz
```

```
export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
export LD_RUN_PATH=/usr/local/lib:$LD_RUN_PATH

#echo "# default configuration" >  /etc/ld.so.conf.d/usr-local.conf
#echo "/usr/local/lib"          >> /etc/ld.so.conf.d/usr-local.conf
#echo "/usr/local/lib64"        >> /etc/ld.so.conf.d/usr-local.conf
#ldconfig
```

```
tar zxvf zlib-1.2.13.tar.gz
cd zlib-1.2.13
./configure --shared
make
make install
cd ..
```

```
tar zxvf expat-2.5.0.tar.gz
cd expat-2.5.0
./configure --without-xmlwf                 \
            --without-examples              \
            --without-tests
make
make install
cd ..
```

```
tar zxvf libressl-3.6.1.tar.gz
cd libressl-3.6.1
./configure
make
make install
cd ..
```

```
tar zxvf apr-1.7.0.tar.gz
cd apr-1.7.0
./configure
make
make install
cd ..
```

```
tar zxvf apr-util-1.6.1.tar.gz
cd apr-util-1.6.1
./configure --with-apr=/usr/local/apr                           \
            --with-expat=/usr/local                             \
            --with-crypto                                       \
            --with-openssl=/usr/local                           \
            --with-ldap
make
make install
cd ..
```

```
tar zxvf pcre2-10.39.tar.gz
cd pcre2-10.39
./configure
make
make install
cd ..
```

```
tar zxvf httpd-2.4.54.tar.gz
cd httpd-2.4.54
./configure --with-apr=/usr/local/apr                           \
            --with-apr-util=/usr/local/apr                      \
            --with-ssl=/usr/local                               \
            --enable-so                                         \
            --enable-module=so                                  \
            --with-z=/usr/local                                 \
            --with-pcre=/usr/local                              \
            --enable-mods-shared="reallyall"
make
make install
cd ..
```
