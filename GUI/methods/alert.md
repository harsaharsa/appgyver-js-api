# AG.GUI.alert

## Summary
`alert()` shows a native alert message. The title and message content are set separately. Note that the alert dialogue disrupts JavaScript execution, which can cause problems with for example event listeners.

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
* iOS