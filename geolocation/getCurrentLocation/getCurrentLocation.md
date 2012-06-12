# AG.geolocation.getCurrentLocation

## Summary
`getCurrentLocation()` retrieves the device's current geolocation (GPS coordinates). 

Upon calling the method, the user will receive a native prompt where the application asks to use geolocation. If the request is denied, geolocation information cannot be returned. If the request is accepted, geolocation information is returned, and no further prompts will appear.

## Syntax
`AG.geolocation.getCurrentLocation(successCallback(coords), failureCallback)`

## Parameters

*function* **successCallback**

A function that is run when the coordinates are retrieved successfully. The function takes as a parameter a string that contains the GPS coordinates in the syntax: `latitude,longitude`.

*function* **failureCallback** *`optional`* 

A function that is run when the coordinates can not be retrieved. If it is missing, the method fails silently.

## Returns 
[AG.Deferred()](../../Deferred.md)

## Quick example:

	AG.geolocation.getCurrentLocation(function(coords){
  		AG.GUI.alert("Your GPS coordinates are:", coords);
	})

## Supported platforms
* iOS