# AG.gyroscope.startTracking

## Summary

`startTracking()` starts gyroscope tracking, i.e. starts sending gyroscope data to all gyroscope event listeners in the current view. When this happens, callback functions defined via [`AG.gyroscope.addEventListener`](addEventListener.md) get triggered every time the gyroscope's values change (i.e. the device changes orientation).

By default, the device orientation is not tracked. The gyroscope must be switched on by this method. Gyroscope tracking is also view-specific, so this method only affects gyroscope event listeners in the current view.

If this method is called while gyroscope tracking is active, it does nothing.

## Quick example:

```javascript
	AG.gyroscope.startTracking();
```

## Syntax

```javascript
	AG.gyroscope.startTracking()
```

**Parameters**

None.

## Native layer details, iOS

The method creates an internal event listener for the current view. The event listener listens for a `deviceorientation` event from the mobile device. Once this event is registered (i.e. the device motion has changed), the gyroscope data are retrieved from the native API. They are then passed on as parameters to the callback functions of every gyroscope event listener in the current view, and the callback functions get triggered.

This method sets the [`AG.gyroscope.listener`](listener.md) property to point to the internal function that retrieves the gyroscope data from the native API. Checking if the property is non-null is a good way to see if gyroscope tracking is currently active for this view.

## Returns 

Nothing.

## Supported platforms
* iOS