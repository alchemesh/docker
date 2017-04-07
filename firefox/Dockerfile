# Firefox with pulseaudio
#	docker run -itd \
#	-v /etc/localtime:/etc/localtime:ro \
#	-v /tmp/.X11-unix:/tmp/.X11-unix \
#	-v $HOME/.Xauthority:/home/firefox/.Xauthority \
#	-e DISPLAY=$DISPLAY \
#	--device /dev/snd \
#	--device /dev/video0 \ 
#	-v /etc/machine-id:/etc/machine-id \
#	-v /var/run/dbus:/var/run/dbus \
#	--link pulseaudio:pulseaudio \
#	-e PULSE_SERVER=pulseaudio \
#	--net=shadow-net \
#	--name firefox \
# 	firefox/docker
#
#
#
#
#


FROM debian:unstable

RUN echo "deb http://ftp.us.debian.org/debian/ unstable main contrib non-free" | tee -a /etc/apt/sources.list
RUN echo "deb-src http://ftp.us.debian.org/debian/ unstable main contrib non-free" | tee -a /etc/apt/sources.list

RUN apt-get update && apt-get install -y --no-install-recommends \ 
			libasound2 \
			libpulse0:amd64 \
			firefox \
			&& rm -rf /var/lib/apt/lists/*

# Replace 1000 with your user / group id
RUN groupadd -g 1000 firefox \
	
	&& useradd --create-home -d /home/firefox -g firefox -u 1000 firefox \
	&& usermod -a -G audio,video firefox


USER root
ENV DISPLAY :0
ENV HOME /home/firefox


ENTRYPOINT /bin/bash



