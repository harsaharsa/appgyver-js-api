# AG.accelerometer.stopTracking

## Summary

`stopTracking()` stops accelerometer tracking, i.e. stops sending accelerometer data to all accelerometer event listeners in the current view.

By default, the device orientation is not tracked. The accelerometer must be switched on by the [`AG.accelerometer.startTracking`](startTracking.md) method. Accelerometer tracking is also view-specific, so this method only affects accelerometer event listeners in the current view.

If this method is called while accelerometer tracking is not active, it does nothing.

## Quick example:

```javascript
	AG.accelerometer.stopTracking();
```

## Syntax

```javascript
	AG.accelerometer.stopTracking()
```

**Parameters**

None.

## Native layer details, iOS

The method removes from the current view the internal event listener that tracks device orientation changes and triggers the accelerometer event listeners' callback functions. After calling this method, the accelerometer event listeners are inactive until the [`AG.accelerometer.startTracking`](startTracking.md) method is called again.

This method sets the [`AG.accelerometer.listener`](listener.md) property to null. Checking if the property is null is a good way to see if accelerometer tracking is currently inactive for this view.

## Returns 

Nothing.

## Supported platforms
* iOS