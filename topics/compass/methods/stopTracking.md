# AG.compass.stopTracking

## Summary

`stopTracking()` stops compass tracking, i.e. stops sending compass data to all compass event listeners in the current view.

By default, the device orientation is not tracked. The compass must be switched on by the [`AG.compass.startTracking`](startTracking.md) method. Compass tracking is also view-specific, so this method only affects compass event listeners in the current view.

If this method is called while compass tracking is not active, it does nothing.

## Quick example:

```javascript
	AG.compass.stopTracking();
```

## Syntax

```javascript
	AG.compass.stopTracking()
```

**Parameters**

None.

## Native layer details, iOS

The method removes from the current view the internal event listener that tracks device orientation changes and triggers the compass event listeners' callback functions. After calling this method, the compass event listeners are inactive until the [`AG.compass.startTracking`](startTracking.md) method is called again.

This method sets the [`AG.compass.listener`](listener.md) property to null. Checking if the property is null is a good way to see if compass tracking is currently inactive for this view.

## Returns 

Nothing.

## Supported platforms
* iOS