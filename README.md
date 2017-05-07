# Dockerized Caddy

A [Docker](https://docker.com) image for [Caddy](https://caddyserver.com).

Example Caddyfile:
```Caddyfile
domain.tld {
    root /srv/data/domain
    gzip
    tls /srv/certs/domain/cert.pem /srv/certs/domain/key.pem
    tls off
}
```

Run container:
```sh
docker run -it --rm \
	-v $(pwd)/Caddyfile:/srv/conf/Caddyfile \
	-v $(pwd)/data:/srv/data \
	-v $(pwd)/certs:/srv/certs \
	--name caddy michaelk/caddy
```
