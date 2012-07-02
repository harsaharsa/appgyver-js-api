# AG.navigation.showBackButton

## Summary
`showBackButton()` is an internal method that shows the native back button according to the current view's navigation history array's size.

When the current view's history document array has items, the back button is shown. Tapping the back button triggers the [`AG.navigation.goBack`](goBack.md) method.
 
If you wish to use your own back button or link with AppGyver's navigation history, you can override this method. The navigation extension runs this method when the page is loaded and the history array has content. Overriding this method can useful for example when developing a fullscreen application that doesn't use the native UI elements.

## Quick example:
```javascript
AG.navigation.showBackButton();
```

## Syntax
```javascript
AG.navigation.showBackButton()
```

**Parameters**

No parameters.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS