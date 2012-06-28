# AG.GUI.showNavigationBarRightButton

## Summary
`showNavigationBarRightButton()` shows the native top right button in the navigation bar.

The recurring callback function is triggered when the button is tapped.

The success callback function is triggered if the button was set successfully. If not, the failure callback function is triggered.

This method currently works only in Edge mode.

## Quick example:
```javascript
var hello = function() { AG.GUI.alert("Hello!")}

AG.GUI.showNavigationBarRightButton("Say hello", hello);
```

## Syntax
```javascript
AG.GUI.showNavigationBarRightButton(title, recurringCallback, successCallback, failureCallback)
```

**Parameters**

* *string* **title**<br>
  The text shown on the button.
* *function* **recurringCallback**<br>
  A function that gets called every time the button is tapped.
* *function* **successCallback**<br>
  The success callback function.
* *function* **failureCallback**<br>
  The failure callback function.

## Returns
Nothing.

## Supported platforms
* iOS