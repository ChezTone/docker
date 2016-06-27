FROM debian:jessie
#install tools
RUN apt-get install -y git nodejs &&
    npm install -g grunt-cli bower &&
    apt-get install apache2
#get sources
RUN cd /var/temp
RUN git clone 'https://github.com/ChezTone/cheztone-frontend.git'
RUN npm install && bower install && grunt build
RUN rm -rf /var/www/html/*
RUN cp dist/* /var/www/html
