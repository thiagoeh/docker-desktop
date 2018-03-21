# Base image for running java desktops apps using the ORACLE build
# The Oracle license is automatically accepted, and by using this image you are automatically those terms
# Please do not push this image to a public registry (i.e: Docker Hub)

# After having created this Dockerfile I've noticed that is similar to this one:
#   https://github.com/dockerfile/java/blob/master/oracle-java8/Dockerfile


FROM ubuntu:16.04
MAINTAINER Thiago Hickmann

RUN apt-get update \
        && apt-get install -y software-properties-common debconf-utils \
        && add-apt-repository ppa:webupd8team/java -y \
        && apt-get update \
        && sh -c 'echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 select true" | debconf-set-selections' \
        && apt-get install --yes oracle-java8-installer \
        && apt-get install --yes oracle-java8-set-default \
        && rm -rf /var/cache/oracle-jdk8-installer \
        && apt-get autoremove --yes --purge software-properties-common \
        && rm -rf /var/lib/apt/lists/*


# Shows Java version by default
CMD ["/usr/bin/java","-version"]
