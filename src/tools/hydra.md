# hydra

```bash
paru -S hydra
```

Bruteforce tool.
Protocols supported include FTP, HTTP(S), SMTP, SNMP, XMPP, SSH, and more.
More information: <https://github.com/vanhauser-thc/thc-hydra>.

Guess SSH credentials using a given username and a list of passwords:

```bash
hydra -l username -P <WORDLIST> <IP> ssh
```