# AG.Deferred

The appgyver.js core comes with an implementation of Deferred objects, to provide a different way for asynchronously execute code after an API call or other event succeeds or fails. Instead of defining success and failure callback functions as parameters of the method call, most API calls return an AG.Deferred object.

If you're familiar with jQuery, AG.Deferred works very much like jQuery's Deferred objects, although with only minimal functionalities implemented.

The returned Deferred object waits until some event or user interaction is over, and then sets itself into resolved or rejected state (depending on if the event succeeded or failed). A Deferred object in resolved state will execute the `Deferred.done` function. A Deferred object in rejected state will execute the `Deferred.fail` function. Additionally, you can define a `Deferred.always` function that will be executed in both cases.

The Deferred object thus provides basically the same functionalities as success and failure callbacks, but cleans up the code a bit. Note that a Deferred object can only be resolved or rejected once. It is also possible to add `done`, `fail` and `always` callback functions after the Deferred object is resolved or rejected. These functions will then be executed accordingly.

If the method passes back some data in the form of a callback parameter, the same parameters are available for `Deferred.done` and `Deferred.fail` callbacks. 'Deferred.always' gets either the success or failure callback parameters, depending on if the Deferred was resolved or rejected. Check each method's API documents for more information.

## Example

```javascript
  // Creating the deferred object, note that the successCallback 
  // and failureCallback functions are left out:
  var deferredLoc = AG.geolocation.getCurrentLocation();

  // Defining the callback for resolved state:
  deferredLoc.done(function(coords) {
    AG.GUI.alert("Your coordinates are:" + coords);
  });

  // Defining the callback for rejected state:
  deferredLoc.fail(function(){
    AG.GUI.alert("Could not retreive coordinates.");
  });

  // Defining the callback for both states:
  deferredLoc.always(function(){
    AG.GUI.alert("Deferred was resolved or rejected.");
  });

  // Setting the Deferred object into resolved state manually.
  // The arguments given are passed on to the Deferred.done function as parameters:
  deferredLoc.resolve("In Siberia");

  // Setting the Deferred object into rejected state manually:
  deferred.reject();
```