FROM resin/generic-armv7ahf-buildpack-deps:stretch-scm

RUN apt-get update && apt-get install -y \
		autoconf \
		build-essential \
		imagemagick \
		libbz2-dev \
		libcurl4-openssl-dev \
		libevent-dev \
		libffi-dev \
		libglib2.0-dev \
		libjpeg-dev \
		libmagickcore-dev \
		libmagickwand-dev \
		libmysqlclient-dev \
		libncurses-dev \
		libpq-dev \
		libreadline-dev \
		libsqlite3-dev \
		libssl-dev \
		libxml2-dev \
		libxslt-dev \
		libyaml-dev \
		zlib1g-dev \
	&& rm -rf /var/lib/apt/lists/*
