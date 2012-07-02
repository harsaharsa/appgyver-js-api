# AG.geolocation.getCurrentLocation

## Summary
`getCurrentLocation()` retrieves the device's current geolocation (GPS coordinates). 

Upon calling the method, the user will receive a native prompt where the application asks to use geolocation. If the request is denied, geolocation information cannot be returned. If the request is accepted, geolocation information is returned, and no further prompts will appear (see below for more details).

## Quick example:
```javascript
	AG.geolocation.getCurrentLocation(function(coords) {
  		AG.GUI.alert("Your GPS coordinates are:", coords);
	});
```

## Syntax
```javascript
AG.geolocation.getCurrentLocation(successCallback(coords), failureCallback)
```

**Parameters**

* *function* **successCallback**<br>
 Standard success callback function. The callback parameter is a string that contains the GPS coordinates in the syntax: `latitude,longitude`.

* *function* **failureCallback**<br>
 Standard failure callback function.

## Native layer details, iOS

The method polls the native location API and waits a maximum of 10 seconds to get a location. If a location cannot be resolved in this time, the method fails and calls `failureCallback`. If a location is successfully retrieved, `successCallback` is called and the location data is passed on to the callback function as a parameter.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS