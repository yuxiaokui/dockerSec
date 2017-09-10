FROM fedora:latest
MAINTAINER xi4okv

RUN dnf -y install git python
RUN cd /opt && git clone https://github.com/evilcos/xssor2
RUN cd /opt/xssor2 && pip install -r requirement.txt

ENV RHOST 127.0.0.1 

EXPOSE 8000

ENTRYPOINT sed -i "s/xssor.io/$RHOST:8000/g" /opt/xssor2/xssor/payload/probe.js && cd /opt/xssor2 && python manage.py runserver 0.0.0.0:8000
