FROM jenkins/jenkins:2.426.3-lts

USER root

RUN jenkins-plugin-cli -p ansicolor

RUN echo "Europe/Warsaw" > /etc/timezone &&\
    dpkg-reconfigure --frontend noninteractive tzdata &&\
    date

RUN apt-get update && apt-get install -y sshpass python3-pip
RUN pip3 install ansible --break-system-packages

RUN mkdir ~/.ssh
RUN ssh-keyscan -H github.com >> ~/.ssh/known_hosts