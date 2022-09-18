# install
## install from source
```
cd /usr/local/src/
```

```
# download source

apt-get install -y unzip wget
apt-get install -y libldap2-dev

zypper --non-interactive install wget gzip
zypper --non-interactive install openldap2-devel file

wget https://www.zlib.net/zlib-1.2.12.tar.gz
wget https://github.com/libexpat/libexpat/releases/download/R_2_4_8/expat-2.4.8.tar.gz
wget https://www.openssl.org/source/openssl-1.1.1q.tar.gz

wget https://dist.apache.org/repos/dist/release/apr/apr-1.7.0.tar.gz
wget https://dist.apache.org/repos/dist/release/apr/apr-util-1.6.1.tar.gz
wget --content-disposition https://sourceforge.net/projects/pcre/files/pcre/8.45/pcre-8.45.tar.gz/download

wget https://dist.apache.org/repos/dist/release/httpd/httpd-2.4.54.tar.gz

```

```
tar zxvf zlib-1.2.12.tar.gz
cd zlib-1.2.12
./configure --shared
make
make install
cd ..
```

```
tar zxvf expat-2.4.8.tar.gz
cd expat-2.4.8
./configure --without-xmlwf                 \
            --without-examples              \
            --without-tests
make
make install
cd ..
```

```
tar zxvf openssl-1.1.1q.tar.gz
cd openssl-1.1.1q
./config    --with-zlib-include=/usr/local  \
            --with-zlib-lib=/usr/local      \
            shared zlib-dynamic
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
tar zxvf pcre-8.45.tar.gz
cd pcre-8.45
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
            --with-ssl=/usr/local/ssl                           \
            --enable-so                                         \
            --enable-module=so                                  \
            --with-z=/usr/local                                 \
            --with-pcre=/usr/local                              \
            --enable-mods-shared="reallyall"
make
make install
cd ..
```
