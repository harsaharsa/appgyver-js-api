# AG.gyroscope.stopTracking

## Summary

`stopTracking()` stops gyroscope tracking, i.e. stops sending gyroscope data to all gyroscope event listeners in the current view.

By default, the device orientation is not tracked. The gyroscope must be switched on by the [`AG.gyroscope.startTracking`](startTracking.md) method. Gyroscope tracking is also view-specific, so this method only affects gyroscope event listeners in the current view.

If this method is called while gyroscope tracking is not active, it does nothing.

## Quick example:

```javascript
	AG.gyroscope.stopTracking();
```

## Syntax

```javascript
	AG.gyroscope.stopTracking()
```

**Parameters**

None.

## Native layer details, iOS

The method removes from the current view the internal event listener that tracks device orientation changes and triggers the gyroscope event listeners' callback functions. After calling this method, the gyroscope event listeners are inactive until the [`AG.gyroscope.startTracking`](startTracking.md) method is called again.

This method sets the [`AG.gyroscope.listener`](listener.md) property to null. Checking if the property is null is a good way to see if gyroscope tracking is currently inactive for this view.

## Returns 

Nothing.

## Supported platforms
* iOS