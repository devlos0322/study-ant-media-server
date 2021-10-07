FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y wget net-tools netcat tar vim
RUN apt-get install -y openssh-client
RUN apt-get install -y openssl
RUN apt install sudo
RUN mkdir -p /app
WORKDIR /app
COPY ./resource/ant-media-server-enterprise-2.3.0-20210302_1432.zip /app/ant-media-server-enterprise-2.3.0-20210302_1432.zip

CMD ["/bin/bash"]

EXPOSE 1935 5080 5443

# docker build . -t ubuntu-client
# docker run -it ubuntu-client
# docker exec -it e1a3d22a0f83 /bin/bash