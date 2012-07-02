# AG.gyroscope.listener

## Summary
`listener` is a property that references to the native event listener added to a view by [`AG.gyroscope.startTracking`](startTracking.md). It shouldn't be manipulated directly, but checking if it is `null` is a good way to see if gyroscope tracking is active for the current view.

Every view has its unique `AG.gyroscope.listener` property.

## Quick example:
```javascript
	if (AG.gyroscope.listener === null) {
	    AG.GUI.alert("The gyroscope isn't tracking!")
	}
```

## Contains:

A reference to a native event listener listening for `deviceorientation` events in the current view. 

For new views, the property is `null`. Calling `startTracking` sets the property to reference the event listener, and calling `stopTracking` sets it to `null` again.

## Supported platforms:
* iOS