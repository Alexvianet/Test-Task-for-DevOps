# Test-Task-for-DevOps
Using docker, setup containers that communicate to each other (see simple dia-
gram below):
1. application server with simple, static content and log agent which parsing
app's logs and pushing them to log forwarder
2. log forwarder which receives log traffic from log agent(s) and pushing them
to logging store server. Optionally, pushing logs to external storage too
3. logging store server which stores all incoming logs locally

Please ensure that the app's access logs are going to the logging store server via the logging
agent and log forwarder.

The ideal solution here should be re-usable. In production we would want to run one log-
ging agent and many app server instances together on any host. This would provide us with
an easy way to ship logs for each container from each docker host to the centralized logging
store.

A good solution will include the ability to easily configure the address of the for logging for-
warder (it may be changed so just re-configuring the logging agent should be easy). We
should also be able to easily choose what files we want to ship to the logging forwarder.

Your solution should be organised as repository on Github with shell, Dockerfile(s), and any
other files/scripts as needed.

You are free to use any base image (s) or logging/application services, take those you most
familiar with!

Extra: as optional external log storage you may use anything (S3, ES). Think about possible
issues when log forwarder is a group of servers.


# Resolution:

1 application server - myapp (apache)

2 log agent which parsing app's logs (filebeat) filebeat.yml can be reconfigured for changing the address of the for logging forwarder and choose what files we want to ship to the logging forwarder

3 log forwarder (Logstash) pipelines can be reconfigured to use also S3 like external log storage, esey to scale (https://www.elastic.co/guide/en/logstash/current/deploying-and-scaling.html)

4 logging store server (ES)
