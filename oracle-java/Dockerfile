# Base image for running java desktops apps using the ORACLE build
# The Oracle license is automatically accepted, and by using this image you are automatically those terms

FROM ubuntu:16.04
MAINTAINER Thiago Hickmann

RUN apt-get update \
        && apt-get install -y software-properties-common debconf-utils \
        && add-apt-repository ppa:webupd8team/java -y \
        && apt-get update 
RUN echo "Forcing another layer 1..."  
RUN sh -c 'echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 select true" | debconf-set-selections' 
RUN echo "Forcing another layer 4..." \ 
        && apt-get install --yes oracle-java8-installer 
RUN echo "Forcing another layer 5..." \ 
        && apt-get install --yes apt-get install oracle-java8-set-default 
RUN echo "Forcing another layer 6..." \
        && rm -rf /var/cache/oracle-jdk8-installer 
        ## FIXME This breaks apt: ##  && apt-get autoremove --yes --purge software-properties-common \
RUN echo "Forcing another layer 7..." \ 
        && rm -rf /var/lib/apt/lists/*
