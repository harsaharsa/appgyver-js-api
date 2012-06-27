# AG.gyroscope #

The **AG.gyroscope** namespace contains methods that give access to the mobile device's gyroscope, allowing you to track the device's orientation in physical space.

You can add gyroscope event listeners to the current view. When you add an event listener, you give it a callback function as a parameter. The callback function gets triggered every time the gyroscope registers a change (i.e. the device orientation is changed). When the callback function is triggered, it receives fresh gyroscope data as parameter objects.

You can have multiple gyroscope event listeners per view. When you call the `AG.gyroscope.startTracking` method, all of them start receiving gyroscope data. The gyroscope tracking is view-specific, so if you have other gyroscope event listeners in other views, you need to call `startTracking` or `stopTracking` separately there.

## Methods ##
* [AG.gyroscope.addEventListener](methods/addEventListener.md)
* [AG.gyroscope.removeAllEventListeners](methods/removeAllEventListners.md)
* [AG.gyroscope.removeEventListener](methods/removeEventListener.md)
* [AG.gyroscope.startTracking](methods/startTracking.md)
* [AG.gyroscope.stopTracking](methods/stopTracking.md)

## Full example ##

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {
      window.gyroscope_listener = AG.gyroscope.addEventListener(function(alpha,beta,gamma){
        document.getElementById("gyro_alpha").innerHTML = alpha;
        document.getElementById("gyro_beta").innerHTML = beta;
        document.getElementById("gyro_gamma").innerHTML = gamma;
      });
      
      document.getElementById("toggle_gyro_tracking").addEventListener("click", function(e){
        e.preventDefault();
        if (AG.gyroscope.listener === null) {
          AG.gyroscope.startTracking();
        } else {
          AG.gyroscope.stopTracking();
        }
      });
      
      document.getElementById("remove_listener").addEventListener("click", function(e){
        e.preventDefault();
        AG.gyroscope.removeEventListener(window.gyroscope_listener);
      });
    }, false);
    </script>
    <style>
      td:nth-child(2){
        text-align:right;
      }
    </style>
  </head>
  <body>
    <h1>AG.gyroscope example</h1>
    <h2>Gyroscope values:</h2><a href="#" data-navigation="false" id="toggle_gyro_tracking">Toggle gyroscope tracking</a><br />
    <table style="width:100%;">
      <tr>
        <td colspan="2"><b>values:</b></td>
      </tr>
      <tr><td>The rotation, in degrees, of the device frame around its z-axis (alpha angle): </td><td id="gyro_alpha"></td></tr>
      <tr><td>The rotation, in degrees, of the device frame around its x-axis (beta angle):</td><td id="gyro_beta"></td></tr>
      <tr><td>The rotation, in degrees, of the device frame around its y-axis (gamma angle):</td><td id="gyro_gamma"></td></tr>
    </table>
    <p><a href="#" data-navigation="false" id="remove_listener">Remove listener</a></p>

  </body>
</html>
```