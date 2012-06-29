# AG.navigation.goBack

## Summary
`goBack()` navigates the current view to the last item in the navigation history array, using a native transition animation.

When the current view's navigation history array has content, this function will navigate the current view to the file path stored in the last item of the history array.

## Quick example:
```javascript
AG.navigation.goBack();
```

## Syntax
```javascript
AG.navigation.goBack()
```

**Parameters**

No parameters.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS