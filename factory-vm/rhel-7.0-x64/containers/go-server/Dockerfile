################################################################################
#
# Go Server
#
#    docker build -rm=true -t fans/go-server .
#    CONTAINER=$(docker run -d -p 2000:22 -p 8153:8153 -t fans/go-server)
#    ssh -X -l docker -p 2000 localhosts
#
################################################################################

FROM        fans/oraclejdk7:latest
MAINTAINER  Chris Phillipson <fastnsilver@gmail.com>


ENV 	GO_SERVER_VERSION 14.2.0-377
ENV 	JAVA_HOME /usr/java/default

RUN 	yum install -y wget
RUN 	wget download.go.cd/gocd-rpm/go-server-$GO_SERVER_VERSION.noarch.rpm

RUN		yum --nogpgcheck -y localinstall go-server-$GO_SERVER_VERSION.noarch.rpm

RUN 	rm -f go-server-$GO_SERVER_VERSION.noarch.rpm

EXPOSE 8153 8154

ADD     etc/supervisor/conf.d/go-server.conf /etc/supervisor/conf.d/go-server.conf