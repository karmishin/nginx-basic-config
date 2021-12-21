# nginx-basic-config

A simple nginx configuration template for HTTPS websites. Tested on Debian 11 with nginx mainline 1.21.4 and openssl 1.1.1k. Based on [ssl-config](https://ssl-config.mozilla.org/).

Quick instructions:

1. Always use the latest version of nginx **mainline** from [nginx.org](https://nginx.org/en/linux_packages.html)
2. Copy the contents of the repository to `/etc/nginx/` and replace all occurrences of `example.com` with your domain name
3. Obtain certs from LetsEncrypt/ZeroSSL/BuyPass/your CA of choice. I use certbot:
```
certbot certonly --nginx
```

Some notes:
* requests without the `Host` header are rejected
* `ssl_reject_handshake` requires nginx 1.19.4+
* HSTS (Strict-Transport-Security) is enabled, [learn what this means](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security) before proceeding


