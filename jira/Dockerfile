FROM frolvlad/alpine-oraclejdk8:full

RUN mkdir -pv /var/jira &&\
		wget https://www.atlassian.com/software/jira/downloads/binary/atlassian-jira-software-7.9.1.tar.gz && \
		tar xzf atlassian-jira-software-7.9.1.tar.gz -C /opt && \
		mv /opt/atlassian-jira-software-7.4.2-standalone /opt/jira
COPY mysql-connector-java-8.0.11.jar /opt/jira/lib/
ENV JAVA_HOME="/usr/lib/jvm/default-jvm"
ENV JIRA_HOME="/var/jira"
VOLUME ["/opt/jira","/var/jira"]
EXPOSE 8080
CMD ["/opt/jira/bin/start-jira.sh"]
