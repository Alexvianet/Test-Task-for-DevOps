# https://github.com/elastic/logstash-docker
FROM docker.elastic.co/logstash/logstash-oss:6.1.0
RUN rm -f /usr/share/logstash/pipeline/logstash.conf
# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
RUN logstash-plugin install logstash-input-beats
