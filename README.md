"# study-ant-media-server" 

# Build
docker build -t antmediaserver --build-arg AntMediaServer=./resource/ant-media-server-enterprise-2.4.0.2-20210905_1241.zip .

# Test
docker run -it -d -p 1935:1935 -p 5080:5080 -p 5443:5443 -p 5000-65000:5000-65000/udp antmediaserver