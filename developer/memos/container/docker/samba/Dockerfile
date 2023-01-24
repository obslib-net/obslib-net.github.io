
FROM ubuntu:bionic AS build

COPY smb.conf /etc/samba/smb.conf

RUN set -eux;                                                                \ 
    apt-get update;                                                          \ 
    apt install -y samba                                                     \ 
    apt-get -y clean;                                                        \ 
    rm -rf /var/lib/apt/lists/*

EXPOSE 137 138 139 445

CMD ["/usr/sbin/smbd", "-F", "-S"]
