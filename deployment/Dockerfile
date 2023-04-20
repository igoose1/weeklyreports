# build static
FROM klakegg/hugo:0.107.0 as builder

WORKDIR /blog
COPY . /blog/
RUN hugo build

# serve static
FROM caddy:2.6.4

COPY --from=builder /blog/public /srv/weekly
COPY deployment/Caddyfile /etc/caddy/Caddyfile
