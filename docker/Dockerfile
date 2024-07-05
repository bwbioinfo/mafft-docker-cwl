# Use a base image
FROM ubuntu:latest

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    wget \
    zlib1g-dev

# Set the working directory
WORKDIR /app

# Download and install MAFFT
RUN wget https://mafft.cbrc.jp/alignment/software/mafft-7.475-with-extensions-src.tgz && \
    tar -xvf mafft-7.475-with-extensions-src.tgz && \
    cd mafft-7.475-with-extensions/core && \
    make && \
    cp mafft /usr/local/bin

# Set the entrypoint
ENTRYPOINT ["mafft"]

# Set the default command
CMD ["--help"]