FROM bitnami/minideb-extras:stretch-r74
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages libbsd0 libc6 libgcc1 libstdc++6 libx11-6 libxau6 libxcb1 libxdmcp6
RUN bitnami-pkg unpack kibana-6.3.1-0 --checksum 94382f43bc9ccc3592c4650356db9d018295be2f5b2f77673f67c223d641b3c3

COPY rootfs /
ENV BITNAMI_APP_NAME="kibana" \
    BITNAMI_IMAGE_VERSION="6.3.1-debian-9-r1" \
    KIBANA_ELASTICSEARCH_PORT_NUMBER="9200" \
    KIBANA_ELASTICSEARCH_URL="elasticsearch" \
    KIBANA_PORT_NUMBER="5601" \
    PATH="/opt/bitnami/kibana/bin:$PATH"

EXPOSE 5601

ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["nami","start","--foreground","kibana"]
