FROM ubuntu:20.04
ARG release_version=LATEST_ORBITRON_RELEASE
RUN apt-get -y update && apt-get -y install libssl-dev libudev-dev curl
RUN curl -sSf https://raw.githubusercontent.com/orbitron-network/orbitron-chain/develop/install/orbitron-install-init.sh | sh -s - LATEST_ORBITRON_RELEASE
ENV PATH="/root/.local/share/orbitron/install/active_release/bin":"$PATH"
COPY entrypoint.sh entrypoint.sh
ENTRYPOINT [ "/usr/bin/sh","-c", "./entrypoint.sh" ]
