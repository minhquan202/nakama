# Description

The Nakama dashboard does not have any limit on the number of failed login attempts in a very short period of time. I can brute force the password without getting locked out of my account

# Proof of Concept

1. Send a login request.
2. Capture the login request
3. Replay the login request with different password value.

HTTP request

```json
POST /v2/console/authenticate HTTP/1.1
Host: api-game.vnshop.vn
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: application/json, text/plain, */*
Accept-Language: vi-VN,vi;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
Content-Type: application/json
Content-Length: 46
Origin: https://admin-game.vnshop.vn
Referer: https://admin-game.vnshop.vn/
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-site
Sec-Gpc: 1
X-Pwnfox-Color: red
Te: trailers
Connection: close

{"username":"blackjame","password":"12345678"}
```

POC: https://www.notion.so/No-Protection-against-Bruteforce-attacks-on-Login-page-in-7133e7c1a78e47f0991c881e029d9414?pvs=4



# Impact

Login Bruteforce attacks
