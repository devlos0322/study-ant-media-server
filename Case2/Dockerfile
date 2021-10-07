# This docker file can be used in kubernetes. 
# It accepts all cluster related parameters at run time. 
# It means it's very easy to add new containers to the cluster 
# https://github.com/ant-media/Scripts/blob/master/docker/Dockerfile_Process
FROM ubuntu:18.04


ARG BranchName=master
ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Seoul
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
COPY ./resource/ant-media-server-enterprise-2.3.0-20210302_1432.zip /home/ant-media-server-enterprise-2.3.0-20210302_1432.zip

#Running update and install makes the builder not to use cache which resolves some updates
RUN apt-get update && apt-get install -y curl libcap2 wget net-tools 


RUN cd home \
    && pwd \
    && wget https://raw.githubusercontent.com/ant-media/Scripts/${BranchName}/install_ant-media-server.sh \
    && chmod 755 install_ant-media-server.sh

RUN cd home \
    && pwd \
    && ./install_ant-media-server.sh -i ant-media-server-enterprise-2.3.0-20210302_1432.zip -s false


# Options 
# -g: Use global(Public) IP in network communication. Its value can be true or false. Default value is false.
#
# -s: Use Public IP as server name. Its value can be true or false. Default value is false.
#
# -r: Replace candidate address with server name. Its value can be true or false. Default value is false
#
# -m: Server mode. It can be standalone or cluster. Its default value is standalone. If cluster mode is 
#     specified then mongodb host, username and password should also be provided
#
# -h: MongoDB host
#
# -u: MongoDB username
#
# -p: MongoDB password

#ENTRYPOINT ["/bin/bash"]
ENTRYPOINT ["/usr/local/antmedia/start.sh"]