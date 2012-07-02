# AG.gyroscope.removeAllEventListeners

## Summary
`removeAllEventListener()` removes all gyroscope event listeners from the current view.

## Quick example:
```javascript
	AG.gyroscope.removeAllEventListeners();
```

## Syntax
```javascript
AG.gyroscope.removeAllEventListeners()
```

**Parameters**

No parameters.

## Native layer details, iOS

All gyroscope event listeners are removed from the current view (the array containing the callback functions is set to an empty array).

## Returns 

Nothing.

## Supported platforms
* iOS