# AG.GUI.showRightButton

## Summary
`showRightButton()` shows the native top right button in the navigation bar.

The recurring callback function is triggered when the button is tapped.

This method works only in normal mode.

## Quick example:
```javascript
var hello = function() { AG.GUI.alert("Hello!")}

AG.GUI.showNavigationBarRightButton("Say hello", hello);
```

## Syntax
```javascript
AG.GUI.showNavigationBarRightButton(title, recurringCallback)
```

**Parameters**

* *string* **title**<br>
  The text shown on the button.
* *function* **recurringCallback**<br>
  A function that gets called every time the button is tapped.

## Returns
Nothing.

## Supported platforms
* iOS