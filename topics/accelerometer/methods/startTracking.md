# AG.accelerometer.startTracking

## Summary

`startTracking()` starts accelerometer tracking, i.e. starts sending accelerometer data to all accelerometer event listeners in the current view. When this happens, callback functions defined via [`AG.compass.addEventListener`](addEventListener.md) get triggered every time the compass's values change (i.e. the device changes orientation).

By default, the device orientation is not tracked. The accelerometer must be switched on by this method. Accelerometer tracking is also view-specific, so this method only affects accelerometer event listeners in the current view.

If this method is called while accelerometer tracking is active, it does nothing.

## Quick example:

```javascript
	AG.accelerometer.startTracking();
```

## Syntax

```javascript
	AG.accelerometer.startTracking()
```

**Parameters**

None.

## Native layer details, iOS

The method creates an internal event listener for the current view. The event listener listens for a `devicemotion` event from the mobile device. Once this event is registered (i.e. the device motion has changed), the accelerometer data are retrieved from the native API. They are then passed on as parameters to the callback functions of every accelerometer event listener in the current view, and the callback functions get triggered.

This method sets the [`AG.accelerometer.listener`](listener.md) property to point to the internal function that retrieves the accelerometer data from the native API. Checking if the property is non-null is a good way to see if accelerometer tracking is currently active for this view.

## Returns 

Nothing.

## Supported platforms
* iOS