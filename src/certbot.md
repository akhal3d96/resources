# certbot

In case of custom web server configuration I find DNS challenges more convenient and easier to work with.

```
certbot certonly --manual --preferred-challenges=dns --email email@example.com  -d subdomain.example.com
```