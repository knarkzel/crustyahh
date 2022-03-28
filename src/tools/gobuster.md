# gobuster

```bash
paru -S gobuster
```

Brute-forces hidden paths on web servers and more.
More information: <https://github.com/OJ/gobuster>.

Discover directories and files that match in the wordlist:

```bash
gobuster dir --url <URL> --wordlist <WORDLIST>
```

Discover subdomains:

```bash
gobuster dns --domain <URL> --wordlist <WORDLIST>
```

Fuzz the value of a parameter:

```bash
gobuster fuzz --url <URL>/?parameter=FUZZ --wordlist <WORDLIST>
```
