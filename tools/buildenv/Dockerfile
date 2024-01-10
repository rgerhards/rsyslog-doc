FROM	alpine
LABEL	maintainer rgerhards@adiscon.com
RUN	apk add --no-cache py3-pip py3-sphinx py3-sphinx_rtd_theme git
#RUN	pip install sphinx
#RUN     pip install sphinx_rtd_theme
RUN	adduser -s /bin/ash -D rsyslog rsyslog \
	&& echo "rsyslog ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
WORKDIR	/home/appliance
CMD	["build-doc"]
ENTRYPOINT ["/home/appliance/starter.sh"]
RUN	mkdir /rsyslog-doc
RUN	chmod a+w /rsyslog-doc
VOLUME	/rsyslog-doc
ENV	BRANCH="master" \
	FORMAT="html" \
	STRICT="-n -W"
COPY	starter.sh ./
COPY	tools/* ./tools/
