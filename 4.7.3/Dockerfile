FROM jetty:9.4.6-alpine

ENV FCREPO_VERSION 4.7.3
ENV JAVA_OPTIONS "${JAVA_OPTIONS} -Dfcrepo.modeshape.configuration=classpath:/config/file-simple/repository.json -Dfcrepo.home=/mnt/fedora-data"

ADD https://github.com/fcrepo4/fcrepo4/releases/download/fcrepo-$FCREPO_VERSION/fcrepo-webapp-$FCREPO_VERSION.war $JETTY_BASE/webapps/ROOT.war

RUN chown jetty:jetty $JETTY_BASE/webapps/ROOT.war \
    && mkdir /mnt/fedora-data \
    && chown -R jetty:jetty /mnt/fedora-data

VOLUME /mnt/fedora-data
EXPOSE 8080