FROM rust:1-slim-buster

RUN apt-get update && rm -rf /var/lib/apt/lists/*

ARG DEV_UID=1000
ARG DEV_GID=1000
ARG APP_DIR=/usr/local/src/app

RUN groupadd -g ${DEV_GID} dev \
    && useradd -u ${DEV_UID} -g ${DEV_GID} --no-create-home dev

RUN mkdir -p ${APP_DIR}
RUN chown dev ${APP_DIR}

USER dev

RUN cargo install cargo-watch

WORKDIR ${APP_DIR}