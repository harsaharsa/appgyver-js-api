# AG.GUI.alert

## Summary
`alert()` shows a native alert message. The title and message content are set separately. 

It is a good idea to use `AG.GUI.alert` instead of the regular JavaScript `alert` whenever possible. The regular `alert` blocks JavaScript execution, which can lead to problematic app behavior. Furthermore, the regular alert message's title cannot be set.

## Quick example:
```javascript
AG.GUI.alert("Hello world!" "It's going great.");
```

## Syntax
```javascript
AG.GUI.alert(title, message)
```

**Parameters**

* *string* **title**<br>
  The title of the alert message.
* *string* **message**<br>
  The message body of the alert message.

## Returns
Nothing.

## Supported platforms
* iOS, Android