FROM ubuntu:24.04
RUN apt-get update && apt-get install -y \
 lm-sensors \
 git \
 curl \
 wget \
 libcurl4-openssl-dev \
 libjansson-dev \
 libomp-dev \
 screen \
 && rm -rf /var/lib/apt/lists/*
RUN wget http://ports.ubuntu.com/pool/main/o/openssl/libssl1.1_1.1.0g-2ubuntu4_arm64.deb
RUN dpkg -i libssl1.1_1.1.0g-2ubuntu4_arm64.deb
RUN rm libssl1.1_1.1.0g-2ubuntu4_arm64.deb

RUN mkdir miner
RUN cd miner
COPY ./ccminer miner/ccminer/ccminer
COPY ./config.json miner/ccminer/config.json
RUN chmod +x miner/ccminer/ccminer 

CMD /miner/ccminer/ccminer -c /miner/ccminer/config.json