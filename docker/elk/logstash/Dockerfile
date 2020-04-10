# https://www.docker.elastic.co/
FROM docker.elastic.co/logstash/logstash:7.6.0

RUN rm -f /usr/share/logstash/pipeline/logstash.conf

ADD pipelines.yml /usr/share/logstash/pipeline/logstash.yml
ADD logstash.yml /usr/share/logstash/config/logstash.yml
ADD ./conf.d/patterns/ /etc/logstash/conf.d/patterns/