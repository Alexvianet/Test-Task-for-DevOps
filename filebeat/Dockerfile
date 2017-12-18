FROM docker.elastic.co/beats/filebeat:6.1.0
USER root
RUN chown filebeat /usr/share/filebeat/filebeat.yml && chmod go-w /usr/share/filebeat/filebeat.yml && mkdir /logs
USER filebeat
