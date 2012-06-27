# AG.geolocation #

The **AG.geolocation** namespace contains methods that give access to the device's native geolocation data.

## Methods ##
* [AG.geolocation.getCurrentLocation](methods/getCurrentLocation.md)

## Full example ##

```html
	<!DOCTYPE html>
	<html lang="en">
	  <head>
	    <meta charset="utf-8">
		<title>AG.geolocation examples</title>
	    <script src="../appgyver/appgyver.js"></script>
	    <script>
	    document.addEventListener("DOMContentLoaded", function(){
			
			// Success callback function
	    	function getLocationSuccess(coords) {
	    		AG.GUI.alert("Your GPS coordinates are:", coords);
	    	}
			
			// Failure callback function
	    	function getLocationFail() {
	    		AG.GUI.alert("Error!", "Could not retreive your GPS coordinates.");
	    	}

	    	function locateMe() {
	    		AG.geolocation.getCurrentLocation(getLocationSuccess(str), 
	    										  getLocationFail());
	    	}

	    	document.querySelector("button").addEventListener("touchstart", locateMe());

	    });
	    </script>
	  </head>
	  <body>
	 <h1>AG.geolocation examples</h1>
 
	 <button>Get your current GPS coordinates (getCurrentLocation)</button>
 
	  </body>
	</html>
```