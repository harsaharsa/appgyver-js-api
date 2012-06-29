# AG.navigation.hideBackButton

## Summary
`hideBackButton()` is an internal method that hides the native back button according to the current view's navigation history array's size.

When the current view's history document array is empty, the back button is hidden.
 
If you wish to use your own back button or link with AppGyver's navigation history, you can override this method. The navigation extension runs this method when the page is loaded and the history array does not have content. Overriding this method can useful for example when developing a fullscreen application that doesn't use the native UI elements.

## Quick example:
```javascript
AG.navigation.hideBackButton();
```

## Syntax
```javascript
AG.navigation.hideBackButton()
```

**Parameters**

No parameters.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS