FROM docker.elastic.co/logstash/logstash:7.5.0

RUN rm -f /usr/share/logstash/pipeline/logstash.conf

RUN mkdir /usr/share/logstash/blogs

ADD data/ /usr/share/logstash/blogs/
ADD pipeline/ /usr/share/logstash/pipeline/
ADD config/ /usr/share/logstash/config/