FROM jenkins/ssh-agent:5.12.0-jdk17
ENV DEBIAN_FRONTEND=noninteractive
USER root
RUN apt-get update && apt-get install -y curl python3-pip unzip ansible git
RUN GROUPADD -g <GID DOCKER HOST> docker && usermode -aG docker jenkins
RUN usermod -aG docker jenkins
RUN curl -fsSL https://get.docker.com -o get-docker  | sh 
RUN sh get-docker.sh
RUN pip3 install awscli
RUN curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose
USER jenkins