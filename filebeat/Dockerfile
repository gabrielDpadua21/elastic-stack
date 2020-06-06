FROM docker.elastic.co/beats/filebeat:7.5.0

USER root

RUN mkdir /usr/share/filebeat/datasets

ADD logs/ /usr/share/filebeat/datasets

COPY /config/filebeat.yml /usr/share/filebeat/filebeat.yml

RUN chown root:filebeat /usr/share/filebeat/filebeat.yml

USER filebeat