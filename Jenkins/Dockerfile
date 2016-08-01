FROM jenkins
USER root
RUN apt-get update && apt-get install -y ruby-full rubygems build-essential zip && gem update --system && gem install sass && gem install compass
USER jenkins