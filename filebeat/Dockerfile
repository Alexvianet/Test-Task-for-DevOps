FROM docker.elastic.co/beats/filebeat:6.1.0
COPY filebeat.yml /usr/share/filebeat/filebeat.yml
USER root
RUN chown filebeat /usr/share/filebeat/filebeat.yml && chmod go-w /usr/share/filebeat/filebeat.yml && mkdir /logs
USER filebeat
RUN ./filebeat modules enable apache2
