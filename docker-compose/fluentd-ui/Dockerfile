FROM ruby:2.6.1

EXPOSE 24224
EXPOSE 9292

#VOLUME ["/fluentd-ui-data"]

RUN gem install fluentd-ui

RUN gem install fluentd -v 1.6.2

RUN fluentd-ui setup

CMD ["fluentd-ui", "start"]
