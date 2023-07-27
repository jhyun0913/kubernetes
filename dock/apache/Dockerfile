FROM eldejr/httpd:1.0

ENV REPO=static-web-template
ENV TAG_VERSION=1.2

RUN curl -LJO https://github.com/jhyun0913/${REPO}/archive/refs/tags/v${TAG_VERSION}.tar.gz
RUN tar -zxvf ${REPO}-${TAG_VERSION}.tar.gz
RUN mv ${REPO}-${TAG_VERSION}/* /usr/local/apache2/htdocs