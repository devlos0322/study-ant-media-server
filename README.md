"# study-ant-media-server" 
docker build -t antmediaserver --build-arg AntMediaServer=./resource/ant-media-server-enterprise-2.3.0-20210302_1432.zip .
run -it -p 1935:1935 -p 5080:5080 -p 5443:5443 antmediaserver