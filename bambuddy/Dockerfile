ARG BUILD_FROM=ghcr.io/home-assistant/aarch64-base:3.19
FROM $BUILD_FROM

# Installer dependencies
RUN apk add --no-cache \
    python3 \
    py3-pip \
    git

# Sett working dir
WORKDIR /app

# Clone BambuBuddy
RUN git clone https://github.com/maziggy/bambuddy.git .

# Installer Python deps
RUN pip install --no-cache-dir -r requirements.txt

# Kopier rootfs (s6 overlay scripts)
COPY rootfs /

# Eksponer port
EXPOSE 8000