FROM ubuntu:22.04
RUN apt update
RUN apt upgrade -y
RUN apt install -y wget
RUN mkdir /monitoring
RUN mkdir /monitoring/config
RUN wget https://github.com/prometheus/prometheus/releases/download/v2.53.1/prometheus-2.53.1.linux-arm64.tar.gz
RUN tar -xf ./prometheus-2.53.1.linux-arm64.tar.gz -C /monitoring
RUN rm prometheus-2.53.1.linux-arm64.tar.gz


VOLUME [ "/monitoring/config" ]
EXPOSE 9090
CMD /monitoring/prometheus-2.53.1.linux-arm64/prometheus --config.file=/monitoring/config/prometheus.yml