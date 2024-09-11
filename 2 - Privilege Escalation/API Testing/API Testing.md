____

# Exploiting an API endpoint using documentation

```html
DELETE api/user/carlos
```

# Exploiting server-side parameter pollution in a query string

![[Pasted image 20240911045910.png]]

Adding the additional parameter `field` with variable `reset_token` in the POST request, leak the senitive information to reset password token.