# nc

## Copy text between two sessions on the same server

First session:

```
nc -l -p <PORT>
```

Second session:

```
nc 127.0.0.1 <PORT> # Same port in the first session
```