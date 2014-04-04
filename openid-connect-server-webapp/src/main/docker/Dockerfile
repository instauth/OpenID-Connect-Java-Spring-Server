# Pull base image.
FROM dockerfile/ubuntu

# Install Java
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections
RUN echo debconf shared/accepted-oracle-license-v1-1 seen true | debconf-set-selections
RUN apt-get install -y oracle-java7-installer

RUN apt-get install -y git
RUN apt-get install -y maven

RUN git clone https://github.com/instauth/OpenID-Connect-Java-Spring-Server.git

RUN /usr/bin/mvn -f OpenID-Connect-Java-Spring-Server/pom.xml install

EXPOSE 8080

CMD /usr/bin/mvn -f OpenID-Connect-Java-Spring-Server/openid-connect-server-webapp/pom.xml jetty:run
