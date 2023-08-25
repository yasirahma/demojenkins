# Use the latest CentOS image as the base
FROM centos:latest

RUN  sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN  sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
RUN yum update -y
# Install necessary packages
RUN yum update -y && \
    yum install -y java-17-openjdk && \
    yum clean all


# Set JAVA_HOME environment variable
ENV JAVA_HOME /usr/lib/jvm/java-17-openjdk

# Set PATH to include Java binaries
ENV PATH $PATH:$JAVA_HOME/bin

# Set working directory
WORKDIR /app

# Define an entry point (this can be customized based on your application)
CMD ["java", "-version"]
