___

https://jwt.io/

https://github.com/wallarm/jwt-secrets/blob/master/jwt.secrets.list
# JWT authentication bypass via unverified signature

![[Pasted image 20240910070802.png]]

# JWT authentication bypass via flawed signature verification

![[Pasted image 20240910071753.png]]

# JWT authentication bypass via weak signing key


```bash
hashcat -m 16500 -a 0 eyJraWQiOiI4ZjMyMTg4Mi1iM2ViLTRlYjItYTg0ZS05YTYyMGMzOTc5MjAiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJwb3J0c3dpZ2dlciIsImV4cCI6MTcyNTk4NDIwNSwic3ViIjoid2llbmVyIn0.r2jYw6UNai3aiU23kDltRmrTu_Epoysi-xv4Su7HnBM /usr/share/wordlists/rockyou.txt
```