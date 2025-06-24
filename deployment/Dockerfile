# build static
FROM floryn90/hugo:0.147.9 AS builder

WORKDIR /blog
COPY . /blog/
RUN hugo build

# serve static
FROM caddy:2.10.0

COPY --from=builder /blog/public /srv/weekly
COPY deployment/Caddyfile /etc/caddy/Caddyfile
