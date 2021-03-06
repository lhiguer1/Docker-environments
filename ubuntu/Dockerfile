FROM ubuntu:latest

ARG username="user1"
ARG password="password"
ARG DEBIAN_FRONTEND=noninteractive

# install some stuff
USER root 
RUN apt-get update 
RUN apt-get install -y \
            sudo \
            gdb \
            apt \
            wget \
            coreutils \
            build-essential \
            git 

# create new user
RUN useradd -s /bin/bash \
            -m $username
RUN echo "$username:$password" | chpasswd
RUN echo "$username ALL=(ALL:ALL) ALL" > /etc/sudoers.d/$username

WORKDIR /home/$username
USER $username

