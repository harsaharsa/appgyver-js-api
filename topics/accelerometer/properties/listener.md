# AG.accelerometer.listener

## Summary
`listener` is a property that references to the native event listener added to a view by [`AG.accelerometer.startTracking`](startTracking.md). It shouldn't be manipulated directly, but checking if it is `null` is a good way to see if accelerometer tracking is active for the current view.

Every view has its unique `AG.accelerometer.listener` property.

## Quick example:
```javascript
	if (AG.accelerometer.listener === null) {
	    AG.GUI.alert("The accelerometer isn't tracking!")
	}
```

## Contains:

A reference to a native event listener listening for `devicemotion` events in the current view. 

For new views, the property is `null`. Calling `startTracking` sets the property to reference the event listener, and calling `stopTracking` sets it to `null` again.

## Supported platforms:
* iOS