FROM quay.io/keycloak/keycloak:latest as builder

ENV KC_HEALTH_ENABLED=true
ENV KC_METRICS_ENABLED=true
ENV KC_FEATURES=token-exchange
ENV KC_DB=postgres
# Install custom providers
RUN curl -sL https://github.com/aerogear/keycloak-metrics-spi/releases/download/2.5.3/keycloak-metrics-spi-2.5.3.jar -o /opt/keycloak/providers/keycloak-metrics-spi-2.5.3.jar
RUN /opt/keycloak/bin/kc.sh build

FROM quay.io/keycloak/keycloak:latest
COPY --from=builder /opt/keycloak/ /opt/keycloak/
WORKDIR /opt/keycloak
RUN touch  server.crt.pem && touch server.key.pem
RUN chmod 755 server.crt.pem
RUN chmod 755 server.key.pem
ENV KC_HOSTNAME=<YOUR_HOSTNAME>
ENV KC_HTTPS_CERTIFICATE_FILE=/opt/keycloak/server.crt.pem
ENV KC_HTTPS_CERTIFICATE_KEY_FILE=/opt/keycloak/server.key.pem
ENV KC_HTTPS_PORT=443
ENV KC_HTTP_PORT=80
ENTRYPOINT ["/opt/keycloak/bin/kc.sh"]
