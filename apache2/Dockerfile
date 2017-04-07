# Apache2
#
# docker run -d \
#	-v /etc/localtime:/etc/localtime:ro \
#	--name apache2-server \
#	-p 80:80 \
#       --net=shadow-net	
#	apache2/docker
#

FROM debian:unstable

LABEL maintainer "Jorrell Smith <jorrells@linux.com>"

RUN apt-get update && apt-get install -y \
	apache2 \
 	php \
	libapache2-mod-php \
	php-mcrypt \
	php-mysql \
	mysql-client \
	--no-install-recommends \
	&& rm -rf /var/lib/apt/lists/*



ENTRYPOINT service apache2 restart && bash 


