FROM node:12-alpine
LABEL maintainer="Evine Deng <evinedeng@foxmail.com>"
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV HOME=/root LANGUAGE=en_US.UTF-8 LANG=en_US.UTF-8 LC_ALL=C
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.bfsu.edu.cn/g' /etc/apk/repositories && \
    apk update -f && \
    apk --no-cache add -f openssl coreutils git wget curl nano tzdata perl bash && \
    rm -rf /var/cache/apk/*
COPY Docker/Entrypoint.sh /Entrypoint.sh
RUN chmod 777 /Entrypoint.sh && \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone
WORKDIR /root
VOLUME /root
ENTRYPOINT /Entrypoint.sh
