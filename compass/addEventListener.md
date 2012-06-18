# AG.compass.addEventListener

## Summary
`addEventListener()` adds a new compass event listener to the current view. 

The event listener's callback function is triggered when the compass is tracking and registers a device orientation change.

## Quick example:
```javascript
	AG.compass.addEventListener(function(heading, accuracy) {
		heading_html_element.textContent = heading;
		accuracy_html_element.textContent = accuracy;
	});
```

## Syntax
```javascript
AG.compass.addEventListener(successCallback(heading, accuracy))
```

**Parameters**

* *function* **successCallback**
 Standard success callback function. The callback parameters are as follows:
  * *double* **heading**
    Compass heading, in degrees relative to magnetic north, increasing clockwise.
  * *double* **accuracy**
    Accuracy of the compass heading, in degrees.

## Native layer details, iOS

The event listener is added for the current view. This is done by including the event listener's callback function into an array of callback functions that get triggered each time the device orientation changes.

See the documentation for the [`AG.compass.startTracking`](starttracking.md) method for more information about how the compass data gets updated.

## Returns 
* *string* **listener_id**
  A string value containing the listener's unique id, to be used with [`AG.compass.removeEventListener(listener_id)`](removeEventListener.md).

## Supported platforms
* iOS