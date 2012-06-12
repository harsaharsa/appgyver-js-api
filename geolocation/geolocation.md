# AG.geolocation API #

The **AG.geolocation** namespace contains methods that give access to the device's native geolocation data.

## Full example ##

	<!DOCTYPE html>
	<html lang="en">
	  <head>
	    <meta charset="utf-8">
		<title>AG.geolocation examples</title>
	    <script src="../appgyver/appgyver.js"></script>
	    <script>
	    document.addEventListener("DOMContentLoaded", function(){

	    	function locationRetrieved(str) {
	    		AG.GUI.alert("Your GPS coordinates are:", str);
	    	}

	    	function getLocationFailed() {
	    		AG.GUI.alert("Error!", "Could not retreive your GPS coordinates.");
	    	}

	    	function locateMe() {
	    		AG.geolocation.getCurrentLocation(locationRetrieved(str), 
	    										  getLocationFailed());
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