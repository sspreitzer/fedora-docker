FROM fedora:22
RUN dnf install -y golang git mercurial && \
    GOPATH=/go go get -v github.com/skynetservices/skydns && \
    GOPATH=/go go build -v github.com/skynetservices/skydns && \
    cp /go/bin/skydns /usr/local/bin/ && \
    rm -rf /go && \
    dnf remove -y golang git mercurial && \
    dnf clean all
ENV ETCD_MACHINES="http://etcd:4001" \
    ETCD_TLSKEY="" \
    ETCD_TLSPEM="" \
    ETCD_CACERT="" \
    SKYDNS_ADDR="0.0.0.0:53" \
    SKYDNS_DOMAIN="skydns.local" \
    SKYDNS_NAMESERVERS="8.8.8.8:53,8.8.4.4:53" \
    SKYDNS_PATH_PREFIX="skydns"
CMD ["/usr/local/bin/skydns"]
EXPOSE 53 53/udp
