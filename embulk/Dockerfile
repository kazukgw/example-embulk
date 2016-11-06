FROM openjdk:8-alpine
RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories
RUN apk update
RUN apk add bash curl jruby tzdata && rm -rf /var/cache/apk/*
RUN curl --create-dirs -o /root/.embulk/bin/embulk -L "http://dl.embulk.org/embulk-latest.jar"
RUN chmod +x /root/.embulk/bin/embulk
ENV PATH /root/.embulk/bin:$PATH
RUN /root/.embulk/bin/embulk gem install embulk-input-mysql embulk-output-bigquery
