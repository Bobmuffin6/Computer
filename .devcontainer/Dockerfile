FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Prevent interactive prompts during build
ENV DEBIAN_FRONTEND=noninteractive

# Code 1: Install XFCE, VNC, NoVNC, and Firefox
RUN apt-get update && apt-get install -y \
    xfce4 xfce4-goodies tightvncserver dbus-x11 websockify novnc wget \
    && install -d -m 0755 /etc/apt/keyrings \
    && wget -q https://packages.mozilla.org/apt/repo-signing-key.gpg -O- | tee /etc/apt/keyrings/packages.mozilla.org.asc > /dev/null \
    && echo "deb [signed-by=/etc/apt/keyrings/packages.mozilla.org.asc] https://packages.mozilla.org/apt mozilla main" | tee -a /etc/apt/sources.list.d/mozilla.list > /dev/null \
    && echo 'Package: *\nPin: origin packages.mozilla.org\nPin-Priority: 1000' | tee /etc/apt/preferences.d/mozilla \
    && apt-get update && apt-get install -y firefox
