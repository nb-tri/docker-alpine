FROM redis
LABEL maintainer="nguyenbatri84@gmail.com"

ENV REDIS_PASSWORD 123qwe

CMD ["sh", "-c", "exec redis-server --requirepass \"$REDIS_PASSWORD\""]