ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

# Installer dependencies
RUN apk add --no-cache \
    python3 \
    py3-pip \
    git \
    build-base \
    linux-headers

# Sett arbeidsmappe
WORKDIR /app

# Clone spesifikk release (IKKE latest!)
ARG BAMBUDDY_VERSION=v1.1.0
RUN git clone --branch ${BAMBUDDY_VERSION} https://github.com/maziggy/bambuddy.git .

# Installer deps
RUN pip install --no-cache-dir -r requirements.txt

# Kopier rootfs
COPY rootfs /

# Eksponer port
EXPOSE 8000