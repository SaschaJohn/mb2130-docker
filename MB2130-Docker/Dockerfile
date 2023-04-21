FROM ubuntu:xenial
RUN apt update
RUN apt-get install -y cups cups-bsd libgs-dev
ADD mccgdi-2.0.10-x86_64.tar.gz /tmp
RUN /tmp/mccgdi-2.0.10-x86_64/install-driver
RUN mkdir /tmp/container
VOLUME ["/mnt/container"]
COPY *.conf /etc/cups
COPY  ppd/* /etc/cups/ppd
EXPOSE 631

ADD entrypoint.sh /
RUN chmod +x /entrypoint.sh

CMD ["/entrypoint.sh"]
#RUN cupsctl --remote-admin --remote-any --share-printers


