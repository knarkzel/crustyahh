# Upgrade dumb shell

```bash
python -c 'import pty; pty.spawn("/bin/bash")'
# Ctrl-Z
stty raw -echo
fg
reset
# Set terminal to vt100
```