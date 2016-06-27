FROM debian:jessie
#install tools
RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_6.x | bash - && \
    apt-get update && apt-get install -y git nodejs && \
    npm install -g grunt-cli bower && \
    apt-get install apache2 -y 
#get sources
RUN mkdir /var/temp 
RUN cd /var/temp && git clone 'https://github.com/ChezTone/cheztone-frontend.git'
#RUN cd /var/temp/cheztone-frontend && npm install && bower install && grunt build
#RUN rm -rf /var/www/html/*
#RUN cp dist/* /var/www/html
