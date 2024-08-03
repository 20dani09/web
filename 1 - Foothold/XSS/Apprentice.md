____

# Reflected XSS into HTML

The value of the **search** request parameter is copied into the HTML document as plain text between tags. 
```js
<script>alert(1)</script> 
```
This input was echoed unmodified in the application's response.


# Stored XSS into HTML 

In the comment section,
```js
<script>alert(1)</script> 
```

