FROM frolvlad/alpine-oraclejdk8:full

RUN mkdir -pv /var/jira &&\
		wget https://s3.cn-northwest-1.amazonaws.com.cn/public-files/atlassian-jira-software-7.2.2.tar.gz && \
		tar xzf atlassian-jira-software-7.2.2.tar.gz -C /opt && \
		mv /opt/atlassian-jira-software-7.2.2-standalone /opt/jira
COPY mysql-connector-java-5.1.39-bin.jar /opt/jira/atlassian-jira/WEB-INF/lib/
COPY atlassian-extras-3.1.2.jar /opt/jira/atlassian-jira/WEB-INF/lib/
ENV JAVA_HOME="/usr/lib/jvm/default-jvm"
ENV JIRA_HOME="/var/jira"
VOLUME ["/opt/jira","/var/jira"]
EXPOSE 8080
CMD ["/opt/jira/bin/start-jira.sh"]
