# AG.compass.removeEventListener

## Summary
`removeEventListener()` removes the compass event listener from the current view that matches the given listener ID. A listener ID is returned by [`AG.compass.addEventListener`](addEventListener.md).

## Quick example:
```javascript
	AG.compass.removeEventListener(listener_id);
```

## Syntax
```javascript
AG.compass.removeEventListener(listener_id)
```

**Parameters**

* *string* **listener_id**<br>
 The ID of the listener to be removed. 

## Native layer details, iOS

The compass event listener with the given ID is removed from the current view (by removing it from the array of event listeners).

## Returns 
* *string* **listener_id**<br>
  A string value containing the listener's unique id, to be used with [`AG.compass.removeEventListener(listener_id)`](removeEventListener.md).

## Supported platforms
* iOS