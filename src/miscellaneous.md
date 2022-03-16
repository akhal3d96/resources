# Miscellaneous

* Invert image colors `gm convert <input> -negate <output>`
* Copy directory recursively `cp -a /source/ /dest/`
* curl basic auth: `curl -u username:password https://example.com`
* Trigger sentry cleanup `docker exec sentry_onpremise_sentry-cleanup_1 gosu sentry sentry cleanup --days <number of days>`
* Check TLS version of a website `openssl s_client -connect example.com:443 -tls1_2`