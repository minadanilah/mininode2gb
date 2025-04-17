# Gunakan Ubuntu 22.04 sebagai base image
FROM ubuntu:22.04

# Install dependency dasar
RUN apt-get update && \
    apt-get install -y curl gnupg2 ca-certificates lsb-release software-properties-common build-essential

# Install Node.js (misalnya versi 18.x)
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs

# Cek versi node & npm
RUN node -v && npm -v

# Install Docker (opsional untuk menjalankan docker di dalam codespace)
RUN apt-get install -y docker.io

# Install libstdc++ versi 3.x (biasanya ini tersedia lewat paket gcc)
RUN apt-get install -y libstdc++6

# Buat direktori kerja
WORKDIR /workspace/app

# Tambahkan user vscode untuk codespace
RUN useradd -m vscode && chown -R vscode /workspace

# Ganti ke user vscode
USER vscode
