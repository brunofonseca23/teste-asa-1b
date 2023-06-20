FROM ubuntu/bind9:latest

RUN apt update -y

RUN apt upgrade -y

RUN apt install nano dnsutils -y

COPY ./named.conf /etc/bind/

COPY ./named.conf.local /etc/bind/

COPY ./db.asa.rn.br /etc/bind/

COPY ./rv.asa.rn.br /etc/bind/

EXPOSE 53/tcp
EXPOSE 53/udp
EXPOSE 953/tcp

CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]