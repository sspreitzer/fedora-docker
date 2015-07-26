FROM fedora:22
RUN dnf install -y etcd && \
    dnf clean all
USER etcd
WORKDIR /var/lib/etcd
VOLUME /var/lib/etcd
ENV ETCD_NAME=default \
    ETCD_DATA_DIR="/var/lib/etcd/default.etcd" \
    ETCD_SNAPSHOT_COUNTER="10000" \
    ETCD_HEARTBEAT_INTERVAL="100" \
    ETCD_ELECTION_TIMEOUT="1000" \
    ETCD_LISTEN_PEER_URLS="http://0.0.0.0:2380" \
    ETCD_LISTEN_CLIENT_URLS="http://0.0.0.0:2379,http://0.0.0.0:4001,http://0.0.0.0:7001" \
    ETCD_MAX_SNAPSHOTS="5" \
    ETCD_MAX_WALS="5" \
    ETCD_CORS="" \
    ETCD_INITIAL_ADVERTISE_PEER_URLS="http://etcd:2380" \
    ETCD_INITIAL_CLUSTER="default=http://etcd:2380" \
    ETCD_INITIAL_CLUSTER_STATE="new" \
    ETCD_INITIAL_CLUSTER_TOKEN="etcd-cluster" \
    ETCD_ADVERTISE_CLIENT_URLS="http://etcd:4001" \
    ETCD_DISCOVERY="" \
    ETCD_DISCOVERY_SRV="" \
    ETCD_DISCOVERY_FALLBACK="proxy" \
    ETCD_DISCOVERY_PROXY="" \
    ETCD_PROXY="off" \
    ETCD_CERT_FILE="" \
    ETCD_KEY_FILE="" \
    ETCD_CLIENT_CERT_AUTH="false" \
    ETCD_TRUSTED_CA_FILE="" \
    ETCD_PEER_CERT_FILE="" \
    ETCD_PEER_KEY_FILE="" \
    ETCD_PEER_CLIENT_CERT_AUTH="false" \
    ETCD_PEER_TRUSTED_CA_FILE="" \
    ETCD_DEBUG="false" \
    ETCD_LOG_PACKAGE_LEVELS=""
EXPOSE 2379 2380 4001
CMD ["/usr/bin/etcd"]
