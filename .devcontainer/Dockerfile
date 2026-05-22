# Base image pinned by digest for course stability.
# Tag at pin time: mcr.microsoft.com/devcontainers/python:1-3.11-bookworm
# To refresh, pull the tag and replace the digest below.
FROM mcr.microsoft.com/devcontainers/python:1-3.11-bookworm@sha256:b726eb94f42fcddb10056835f2c474c9f9e12e717ba2b2d2f9a8b1d78feeb68b

# Install Chromium. We intentionally do NOT install chromium-driver:
# Selenium 4.6+ ships Selenium Manager, which auto-downloads a chromedriver
# matching the installed Chromium and avoids version-skew breakage.
RUN set -eux; \
    rm -f /etc/apt/sources.list.d/yarn.list; \
    apt-get update; \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        chromium \
        ca-certificates \
        fonts-liberation; \
    rm -rf /var/lib/apt/lists/*

ENV CHROME_BIN=/usr/bin/chromium
