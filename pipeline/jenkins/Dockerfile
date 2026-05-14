FROM jenkins/jenkins:2.555.2-lts

USER root

# Install docker
RUN apt-get update && curl -sSL https://get.docker.com/ | sh

USER jenkins

# Install required plugins (git, pipeline, and docker pipeline, stagate view)
COPY --chown=jenkins:jenkins plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli --plugin-file /usr/share/jenkins/ref/plugins.txt