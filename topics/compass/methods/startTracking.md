# AG.compass.startTracking

## Summary

`startTracking()` starts compass tracking, i.e. starts sending compass data to all compass event listeners in the current view. When this happens, callback functions defined via [`AG.compass.addEventListener`](addEventListener.md) get triggered every time the compass's values change (i.e. the device changes orientation).

By default, the device orientation is not tracked. The compass must be switched on by this method. Compass tracking is also view-specific, so this method only affects compass event listeners in the current view.

If this method is called while compass tracking is active, it does nothing.

## Quick example:

```javascript
	AG.compass.startTracking();
```

## Syntax

```javascript
	AG.compass.startTracking()
```

**Parameters**

None.

## Native layer details, iOS

The method creates an internal event listener for the current view. The event listener listens for a `deviceorientation` event. Once this event is registered (i.e. the device orientation has changed), the compass heading and accuracy are retrieved from the native API. They are then passed on as parameters to the callback functions of every compass event listener in the current view, and the callback functions get triggered.

This method sets the [`AG.compass.listener`](listener.md) property to point to the internal function that retrieves the compass data from the native API. Checking if the property is non-null is a good way to see if compass tracking is currently active for this view.

## Returns 

Nothing.

## Supported platforms
* iOS