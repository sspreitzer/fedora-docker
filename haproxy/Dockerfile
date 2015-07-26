FROM sspreitzer/confd:latest
RUN dnf install -y supervisor haproxy && \
    dnf clean all
ENV ETCD_NODE=http://etcd:4001
ADD haproxy.ini /etc/supervisord.d/
VOLUME ["/etc/confd", "/var/log/supervisor", "/etc/haproxy", "/var/lib/haproxy", "/var/log/haproxy.log"]
EXPOSE 80 443
CMD ["/usr/bin/supervisord"]
