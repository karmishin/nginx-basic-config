# nginx-basic-config

A simple nginx configuration template for HTTPS websites. Tested on Debian 11 with nginx mainline 1.21.3 and openssl 1.1.1k. Based on [ssl-config](https://ssl-config.mozilla.org/).

Quick instructions:

1. Use nginx mainline from [nginx.org](https://nginx.org/en/linux_packages.html)
2. Put the `example.com.conf` file into the `/etc/nginx/conf.d/` directory on your webserver.
3. Obtain `ffdhe2048.txt` from ssl-config:
```
curl https://ssl-config.mozilla.org/ffdhe2048.txt > /etc/nginx/ffdhe2048.txt
```
4. Obtain certs from Let's Encrypt or somewhere else. I use certbot:
```
certbot certonly --nginx
```

