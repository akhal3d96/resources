# SSH

## SSH Keys

### Create a passwordless key pair

```
ssh-keygen -t ed25519 -C "email@example.com" -f ./path/to/key/id_ed25519 -N ""
```

## Tunneling

### Local port forwarding

It makes remote server appears as local on a certain local port. You use as many ports as you can by using multiple `-L` with every port.

```
ssh -N -L local_port:127.0.0.1:remote_port user@host
```

### Remote port forwarding

Sometimes called reverse tunneling. It redirects incoming traffic from the server to the client using the `-R` flag.

```
ssh -N -R remote_port:127.0.0.1:local_port user@host
```

### Dynamic port forwarding
Creates a SOCKS5 proxy using the `-D` flag.

```
ssh -N -D 127.0.0.1:local_port user@<remote_server>
```

### Optional flags

| Flag | Usage                               |
|------|-------------------------------------|
| -N   | Don't create an interactive session |
| -f   | Run it in the background            |


## Resources

* [SSH Tunneling Explained
](https://goteleport.com/blog/ssh-tunneling-explained/)