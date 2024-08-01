FROM ubuntu:22.04
RUN apt update
RUN apt upgrade -y
RUN apt install -y wget
RUN mkdir /monitoring
RUN mkdir /monitoring/config
RUN wget https://github.com/prometheus/alertmanager/releases/download/v0.27.0/alertmanager-0.27.0.linux-arm64.tar.gz
RUN tar -xf ./alertmanager-0.27.0.linux-arm64.tar.gz -C /monitoring/
RUN rm alertmanager-0.27.0.linux-arm64.tar.gz


VOLUME [ "/monitoring/config" ]
EXPOSE 9093
CMD /monitoring/alertmanager-0.27.0.linux-arm64/alertmanager --config.file=/monitoring/config/alertmanager.yml