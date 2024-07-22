# Use a base image
FROM ubuntu:latest

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    wget \
    zlib1g-dev

# Set the working directory
WORKDIR /opt

# Download and install MAFFT
RUN wget https://mafft.cbrc.jp/alignment/software/mafft-7.525-with-extensions-src.tgz 
RUN tar -xvf mafft-7.525-with-extensions-src.tgz 

WORKDIR /opt/mafft-7.525-with-extensions/core
RUN make install

RUN mafft --version

CMD [ "mafft" ]