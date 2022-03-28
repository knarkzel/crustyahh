# nmap    

```bash
paru -S nmap
```

Network exploration tool and security / port scanner.
Some features only activate when Nmap is run with privileges.
More information: <https://nmap.org>.

Perform full port, service, version detection scan to determine weaknesses and info:

```bash
sudo nmap -sV -sC -p- <IP>
```
