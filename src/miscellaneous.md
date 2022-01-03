# Miscellaneous

* Invert image colors `gm convert <input> -negate <output>`
* Copy directory recursively `cp -a /source/ /dest/`
* curl basic auth: `curl -u username:password https://example.com`

* Create a passwordless key pair
```
ssh-keygen -t ed25519 -C "email@example.com" -f ./path/to/key/id_ed25519 -N ""
```