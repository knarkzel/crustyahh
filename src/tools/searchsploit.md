# searchsploit

```bash
paru -S exploit-db-git
searchsploit --update
```

Searchsploit searches exploit database's database for exploits, shellcodes
and/or papers. If known version numbers are used as search terms, exploits
for both the exact version and others whose version range covers the one
specified are shown. More information: https://www.exploit-db.com/searchsploit.

Search for an exploit, shellcode, or paper:

```bash
searchsploit search_terms
```

Search for a known specific version, e.g. sudo version 1.8.27:

```bash
searchsploit sudo 1.8.27
```

Show the exploit-db link to the found resources:

```bash
searchsploit --www search_terms
```