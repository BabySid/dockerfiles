#
# Ubuntu Dockerfile
#

# Pull base image.
FROM ubuntu:noble-20260410

# Use China mirrors (Aliyun + Tsinghua) for faster apt.
COPY <<'EOF' /etc/apt/sources.list.d/ubuntu.sources
Types: deb
URIs: http://mirrors.aliyun.com/ubuntu/ http://mirrors.tuna.tsinghua.edu.cn/ubuntu/
Suites: noble noble-updates noble-backports
Components: main restricted universe multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg

Types: deb
URIs: http://mirrors.aliyun.com/ubuntu/ http://mirrors.tuna.tsinghua.edu.cn/ubuntu/
Suites: noble-security
Components: main restricted universe multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
EOF

# Install.
RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y build-essential && \
  apt-get install -y software-properties-common && \
  apt-get install -y curl git htop man unzip vim wget cmake clang libboost-all-dev && \
  apt-get install -y jq tree && \
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs -o rust.sh && sh ./rust.sh -y && rm rust.sh && \
  echo "source $HOME/.cargo/env" >> /root/.bashrc && \
  rm -rf /var/lib/apt/lists/*

# Add files.
# ADD root/.bashrc /root/.bashrc

# Set environment variables.
ENV HOME=/root

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["bash"]
