FROM debian:jessie
#install tools
RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_5.x | bash - && \
    apt-get update && apt-get install -y git nodejs build-essential \
    apache2 ruby ruby-dev
RUN npm install -g grunt-cli bower
RUN chown -R $(whoami) $(npm config get prefix)/lib/node_modules
RUN gem install sass && gem install compass

#get sources
RUN mkdir /var/temp 
RUN node --version
RUN cd /var/temp && git clone 'https://github.com/ChezTone/cheztone-frontend.git'
RUN cd /var/temp/cheztone-frontend && npm install && bower install --allow-root && grunt build
RUN rm -rf /var/www/html/*
RUN cp -r /var/temp/cheztone-frontend/dist/* /var/www/html 

EXPOSE 80

# Launch Apache2
ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
