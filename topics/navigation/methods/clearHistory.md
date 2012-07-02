# AG.navigation.clearHistory

## Summary
`clearHistory()` clears the current view's navigation history.

It does this by overriding the history document stored in remote storage with an empty array.

The returned Deferred object is resolved when the history array is successfully cleared.

## Quick example:
```javascript
AG.navigation.clearHistory();
```

## Syntax
```javascript
AG.navigation.clearHistory()
```

**Parameters**

No parameters.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS