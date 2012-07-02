# AG.gyroscope.removeEventListener

## Summary
`removeEventListener()` removes the gyroscope event listener from the current view that matches the given listener ID. A listener ID is returned by [`AG.gyroscope.addEventListener`](addEventListener.md).

## Quick example:
```javascript
	AG.gyroscope.removeEventListener(listener_id);
```

## Syntax
```javascript
AG.gyroscope.removeEventListener(listener_id)
```

**Parameters**

* *string* **listener_id**<br>
 The ID of the listener to be removed. 

## Native layer details, iOS

The gyroscope event listener with the given ID is removed from the current view (by removing its callback function from the array of event listeners).

## Returns 
* *string* **listener_id**<br>
  A string value containing the listener's unique id, to be used with [`AG.gyroscope.removeEventListener(listener_id)`](removeEventListener.md).

## Supported platforms
* iOS