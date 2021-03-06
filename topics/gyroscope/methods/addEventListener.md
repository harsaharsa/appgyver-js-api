# AG.gyroscope.addEventListener

## Summary
`addEventListener()` adds a new gyroscope event listener to the current view. 

The event listener's success callback function is triggered when the gyroscope is tracking for the current view and registers a change in the device's orientation.

## Quick example:
```javascript
	var listener_id = AG.gyroscope.addEventListener( function(alpha, beta, gamma) {
		// do stuff with the parameters that contain gyroscope data
	});
```

## Syntax
```javascript
AG.gyroscope.addEventListener( successCallback(alpha, beta, gamma) )
```

**Parameters**

* *function* **successCallback**<br>
    The success callback function's callback parameters contain data from the gyroscope, namely the angles of rotation, as follows:

        * *double* **alpha**<br>
          The rotation, in degrees, of the device frame around its z-axis. Values are between 0 and 360.
        * *double* **beta**<br>
          The rotation, in degrees, of the device frame around its x-axis. Values are between -90 and 90.
        * *double* **gamma**<br>
          The rotation, in degrees, of the device frame around its y-axis. Values are between -180 and 180.

            Note that the angles of rotation do not represent the device's real world orientation. They are defined as an offset from an arbitrary direction — typically, the direction in which the device was held when the orientation was first obtained. Therefore, you can only use the angles to track changes in orientation, you cannot derive the direction in which the device is currently facing.

            If the device does not have a gyroscope, these objects are null.

## Native layer details, iOS

The event listener is added for the current view. This is done by including the event listener's callback function into an array of callback functions that get triggered each time the device orientation changes.

The unique ID for each listener is generated by calling ´(new Date).getTime()´.

See the documentation for the [`AG.gyroscope.startTracking`](startTracking.md) method for more information about how the gyroscope data gets updated.

## Returns 
* *string* **listener_id**<br>
  A string value containing the listener's unique id, to be used with [`AG.gyroscope.removeEventListener`](removeEventListener.md).

## Supported platforms
* iOS