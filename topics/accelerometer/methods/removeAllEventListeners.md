# AG.accelerometer.removeAllEventListeners

## Summary
`removeAllEventListener()` removes all accelerometer event listeners from the current view.

## Quick example:
```javascript
	AG.compass.removeAllEventListeners();
```

## Syntax
```javascript
AG.compass.removeAllEventListeners()
```

**Parameters**

No parameters.

## Native layer details, iOS

All compass event listeners are removed from the current view (the array containing the callback functions is set to an empty array).

## Returns 

Nothing.

## Supported platforms
* iOS