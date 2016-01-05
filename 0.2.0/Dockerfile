# Docker file to run Hashicorp Vault (vaultproject.io)

FROM alpine:3.2
# MAINTAINER Stuart Wong <cgs.wong@gmail.com>
# change maintainter until pull
MAINTAINER Bastiaan Bakker <bbakker@xebia.com>

ENV VAULT_VERSION 0.2.0
ENV VAULT_TMP /tmp/vault.zip
ENV VAULT_HOME /usr/local/bin
ENV PATH $PATH:${VAULT_HOME}

RUN apk --update add \
      wget \
      bash \
      ca-certificates &&\
    wget --quiet --output-document=${VAULT_TMP} https://releases.hashicorp.com/vault/0.4.0/vault_${VAULT_VERSION}_linux_amd64.zip &&\
    unzip ${VAULT_TMP} -d ${VAULT_HOME} &&\
    rm -f ${VAULT_TMP}

# Listener API tcp port
EXPOSE 8200

ENTRYPOINT ["/usr/local/bin/vault"]
CMD ["version"]
