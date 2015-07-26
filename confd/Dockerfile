FROM fedora:22
RUN dnf install -y golang git && \
    GOPATH=/go go get -v github.com/constabulary/gb/... && \
    git clone https://github.com/kelseyhightower/confd.git && \
    cd /confd && \
    GOPATH=/go /go/bin/gb build -v all && \
    cd / && \
    cp -v /confd/bin/confd /usr/local/bin/confd && \
    rm -rf /go /confd && \
    dnf remove -y golang git && \
    dnf clean all && \
    useradd -r -m confd && \
    install -d -o confd -g confd -m 0750 /etc/confd && \
    install -d -o confd -g confd -m 0750 /etc/confd/confd.d && \
    install -d -o confd -g confd -m 0750 /etc/confd/templates
