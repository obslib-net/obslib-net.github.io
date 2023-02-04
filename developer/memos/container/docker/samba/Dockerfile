
FROM ubuntu:bionic

RUN set -eux                                                                 \ 
 && apt-get update                                                           \ 
 && apt install -y samba                                                     \ 
 && apt-get -y clean                                                         \ 
 && rm -rf /var/lib/apt/lists/*

COPY smb.conf /etc/samba/smb.conf

EXPOSE 137 138 139 445

CMD ["/usr/sbin/smbd", "-F", "-S"]
