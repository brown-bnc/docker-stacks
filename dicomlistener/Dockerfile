
FROM ubuntu:latest

RUN apt-get update \
  && apt-get install -y python3-pip python3-dev \
  && cd /usr/local/bin \
  && ln -s /usr/bin/python3 python \
  && pip3 install --upgrade pip

RUN apt-get update \
  && apt-get install -y xinetd \
  && apt-get install -y dcmtk \
  && pip install pypx

EXPOSE 4096

RUN mkdir /opt/scripts

COPY ./docker-entrypoint.sh /opt/scripts

ENTRYPOINT ["/opt/scripts/entrypoint.sh"]
#CMD ["service", "xinetd", "start"]
CMD ["/usr/sbin/xinetd", "-dontfork"]