FROM sspreitzer/confd:latest
RUN dnf install -y supervisor nginx && \
    dnf clean all && \
    echo "daemon off;" >> /etc/nginx/nginx.conf
ENV ETCD_NODE=http://etcd:4001
ADD nginx.ini /etc/supervisord.d/
VOLUME ["/etc/confd", "/etc/nginx", "/var/log/supervisor", "/var/log/nginx"]
EXPOSE 80 443
CMD ["/usr/bin/supervisord"]
