FROM multiarch/alpine:armhf-edge

LABEL maintainer="Massimo Gaggero <massimo dot gaggero at crs4 dot it>"

ENV APP_HOME=/opt/datadumper/

# Install required packages
RUN apk add --no-cache python3 git make automake gcc g++ python3-dev && \
	pip3 install virtualenv

RUN \
	mkdir -p ${APP_HOME} && \
	cd ${APP_HOME} && \
	virtualenv venv && \
	. venv/bin/activate && \
	pip3 install influxdb numpy && \
	pip3 install pandas

WORKDIR ${APP_HOME}

ENTRYPOINT ["/bin/sh"]

CMD [ ]
