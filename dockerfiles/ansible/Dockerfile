FROM python:2.7.11-slim

ENV ANSIBLE_VERSION 2.2.0

RUN set -ex \
	&& buildDeps=' \
		gcc \
		python-dev \
		libffi-dev \
		libssl-dev \
	' \
	&& apt-get update \
	&& apt-get install -y --no-install-recommends $buildDeps \
	&& apt-get install -y openssh-server sshpass \
	&& rm -rf /var/lib/apt/lists/* \
	&& pip install boto boto3 \
	&& pip install ansible==$ANSIBLE_VERSION \
	&& apt-get purge -y --auto-remove $buildDeps

WORKDIR /data

CMD ["/bin/bash"]
