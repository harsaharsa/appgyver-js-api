# AG.compass

The **AG.compass** namespace contains methods that give access to the mobile device's compass, allowing you to track the device's real-world orientation.

You can add compass event listeners to the current view. When you add an event listener, you give it a callback function as a parameter. This function gets triggered every time the compass registers a change (i.e. the device orientation is changed). When the function is triggered, it receives fresh compass data as a parameter object.

You can have multiple compass event listeners in a single view. When you call the `AG.compass.startTracking` method, all of them start receiving compass data. The compass tracking is view-specific, so if you have other compass event listeners in another view, you need to call `startTracking` or `stopTracking` separately there.

## Methods ##
* [AG.compass.addEventListener](methods/addEventListener.md)
* [AG.compass.removeAllEventListeners](methods/removeAllEventListners.md)
* [AG.compass.removeEventListener](methods/removeEventListener.md)
* [AG.compass.startTracking](methods/startTracking.md)
* [AG.compass.stopTracking](methods/stopTracking.md)

## Properties ##

* [AG.compass.listener](properties/listener.md)

## Full example ##

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {

      var headingElement = document.querySelector("#compass_heading");
      var accuracyElement = document.querySelector("#compass_accuracy");
      
      function update(compassHeading, compassAccuracy) {
         headingElement.innerHTML(compassHeading);
         accuracyElement.innerHTML(compassAccuracy);
       }

       function addNew() {
         AG.compass.addEventListener(update);
         AG.GUI.alert("Compass event listener added!"); 
       }

       function removeAll() {
         AG.compass.removeAllEventListeners();
         AG.GUI.alert("Hooray!", "All compass event listeners removed from this view.");
       }

       function toggleTracking() {
         if (AG.compass.listener === null) {
           AG.compass.startTracking();
           AG.GUI.alert("Compass tracking on!")
         } else {
           AG.compass.stopTracking();
           AG.GUI.alert("Compass tracking off!")
         }
       }
      
      var addButton = document.querySelector("#add_listener");
      var removeAllButton = document.querySelector("#remove_all_listeners");
      var toggleButton = document.querySelector("#toggle_compass");
      
      addButton.addEventListener("touchstart", addNew);
      removeAllButton.addEventListener("touchstart", removeAll);
      toggleButton.addEventListener("touchstart", toggleTracking);
      
    });
    </script>
  </head>
  <body>
    <h1>AG.compass example</h1>
    <button id="add_listener">Add new compass event listener</button>
    <br>
    <br>
    <button id="remove_all_listeners">Remove all event listeners in the view</button>
    <br>
    <br>
    <button id="toggle_compass">Toggle compass tracking</button>
    <br>
    <br>
    <strong>Compass heading:</strong> <span id="compass_heading">undefined</span><br>
    <em>(in degrees relative to magnetic north, increasing clockwise)</em><br>
    <br>
    <strong>Compass accuracy:</strong> <span id="compass_accuracy">undefined</span><br>
    <em>(in degrees)</em><br>
  </body>
</html>
```