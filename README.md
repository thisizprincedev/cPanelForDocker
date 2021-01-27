# cPanelForDocker

# Create the Docker image
## Once your code is ready and the Dockerfile is written, all you have to do is create your image to contain your application.

docker build --rm -t centos7-cpanel .

# nstruct Docker to run a container in privileged mode by adding the --privileged option to the run command:

sudo docker run --privileged [image_name]

# Docker Privileged Example:

docker run -itd --name=cPanel  --privileged -p 110:110/tcp -p 143:143/tcp -p 20:20/tcp -p 2077:2077/tcp -p 2078:2078/tcp -p 2082:2082/tcp -p 2083:2083/tcp -p 2086:2086/tcp -p 2087:2087/tcp -p 2095:2095/tcp -p 21:21/tcp -p 22:22/tcp -p 25:25/tcp -p 3306:3306/tcp -p 443:443/tcp -p 465:465/tcp  -p 587:587/tcp -p 80:80/tcp -p 993:993/tcp -p 995:995/tcp centos7-systemd:latest

Test: 
docker inspect --format='{{.HostConfig.Privileged}}' [container_id]

Output:
➜  Projetos_test-sinesio: docker inspect --format='{{.HostConfig.Privileged}}' e3236801e656  
true
