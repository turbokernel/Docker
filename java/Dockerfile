FROM alpine:3.7
ENV JAVA_VERSION=8 \
    JAVA_UPDATE=171 \
    JAVA_BUILD=11 \
    JAVA_PATH=512cd62ec5174c3487ac17c61aaa89e8 \
    JAVA_HOME="/usr/local/java"

RUN apk add --no-cache --virtual=build-dependencies wget ca-certificates unzip && \
    cd "/tmp" && \
    wget --header "Cookie: oraclelicense=accept-securebackup-cookie;" \
        "http://download.oracle.com/otn-pub/java/jdk/${JAVA_VERSION}u${JAVA_UPDATE}-b${JAVA_BUILD}/${JAVA_PATH}/jdk-${JAVA_VERSION}u${JAVA_UPDATE}-linux-x64.tar.gz" && \
    tar -xzf "jdk-${JAVA_VERSION}u${JAVA_UPDATE}-linux-x64.tar.gz" && \
    mkdir -p "/usr/local/java" && \
    mv "/tmp/jdk1.${JAVA_VERSION}.0_${JAVA_UPDATE}" "/usr/local/java-${JAVA_VERSION}-oracle" && \
    ln -s "java-${JAVA_VERSION}-oracle" "$JAVA_HOME" && \
    ln -s "$JAVA_HOME/bin/"* "/usr/bin/" && \
    rm -rf "$JAVA_HOME/"*src.zip && \
    apk del build-dependencies && \
    rm "/tmp/"*
ENV JAVA_HOME /usr/local/java
ENV JRE_HOME $JAVA_HOME/jre
ENV CLASSPATH $JRE_HOME/lib
ENV PATH $JAVA_HOME/bin:$PATH
