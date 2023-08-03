#
# Ubuntu Dockerfile
#

# Pull base image.
FROM ubuntu:mantic-20230801

# Install.
RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y build-essential && \
  apt-get install -y software-properties-common && \
  apt-get install -y curl git htop man unzip vim wget cmake clang curl && \
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs -o rust.sh && sh ./rust.sh -y && rm rust.sh \
  echo "source $HOME/.cargo/env" >> /root/.bashrc \
  rm -rf /var/lib/apt/lists/*

# Add files.
# ADD root/.bashrc /root/.bashrc

# Set environment variables.
ENV HOME /root

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["bash"]
