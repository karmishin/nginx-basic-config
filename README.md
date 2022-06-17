A simple nginx configuration template for HTTPS websites. Tested on Debian 11 with nginx 1.22.0 and openssl 1.1.1n. Partially based on [ssl-config](https://ssl-config.mozilla.org/).

Quick instructions:

1. Obtain SSL certs. I use certbot:
```
certbot certonly --nginx -d example.com -d www.example.com
```
2. Copy the contents of the repository to `/etc/nginx/` and replace all occurrences of `example.com` with your domain name


Some notes:
- `www` subdomain redirects to the apex domain (i.e. visitors of `www.example.com` will be redirected to `example.com`)
- Requests without the `Host` header are rejected
- `ssl_reject_handshake` requires nginx 1.19.4+
- HSTS (Strict-Transport-Security) is enabled, [learn what this means](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security) before proceeding


