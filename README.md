# Docker
Install Docker on Windows 10

Pre requisite 
1. Windows 7 or higher
2. Oracle VirtualBOX

Download install DockerToolbox
https://download.docker.com/win/stable/DockerToolbox.exe
this will download Dcoker Terminal and Kitematic

Find below statement in C:\Program Files\Docker Toolbox\start.sh
"${DOCKER_MACHINE}" create -d virtualbox $PROXY_ENV "${VM}"


and replace it with below statement
"${DOCKER_MACHINE}" create -d virtualbox --virtualbox-no-vtx-check $PROXY_ENV "${VM}"

Start Docker Terminal it will wait for IP, We need to follow few steps

1. Open Windows Firewall
2. Click Advance Setting
3. Click on Inbound Rules
4. Click on New Rules
5. Select Custom and click next until scope step appear
6. Select these IP, then click on ADD
7. open cmd, type ipconfig, find your IP address copy and paste it under This IP Address or Subnet text box
8. Now Click on This IP Address Range for example if your IP Address is 192.12.23.1 then in from textbox give 192.12.23.0 and in to 192.12.23.100
9. Click next and next and after that click  select public profile
10. Give some name ex. DockerIP

docker run --rm -p 2181:2181 -p 3030:3030 -p 8081-8083:8081-8083 -p 9581-9585:9581-9585 -p 9092:9092 -e ADV_HOST=192.168.99.100 landoop/fast-data-dev:latest
