ARG ELK_VERSION 

FROM docker.elastic.co/beats/filebeat:${ELK_VERSION}

# Environment variables
ENV     FILEBEAT_HOME /usr/share/filebeat
ENV PATH $PATH:${FILEBEAT_HOME}

COPY filebeat.yml /usr/share/filebeat/filebeat.yml
USER root
#RUN chown root:filebeat /usr/share/filebeat/filebeat.yml
#USER filebeat
ADD     docker-entrypoint.sh    /entrypoint.sh
RUN     chmod +x /entrypoint.sh
ENTRYPOINT  ["/entrypoint.sh"]
CMD ["start"]
