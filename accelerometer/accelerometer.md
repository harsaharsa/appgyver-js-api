# AG.accelerometer #

The **AG.accelerometer** namespace contains methods that give access to the mobile device's accelerometer, allowing you to track changes in the device's acceleration.

You can add accelerometer event listeners to the current view. When you add an event listener, you give it a callback function as a parameter. The callback function gets triggered every time the accelerometer registers a change (i.e. the device moves). When the callback function is triggered, it receives fresh accelerometer data as parameter objects.

You can have multiple accelerometer event listeners per view. When you call the `AG.accelerometer.startTracking` method, all of them start receiving accelerometer data. The accelerometer tracking is view-specific, so if you have other accelerometer event listeners in other views, you need to call `startTracking` or `stopTracking` separately there.

## Methods ##
* [AG.accelerometer.addEventListener](methods/addEventListener.md)
* [AG.accelerometer.removeAllEventListeners](methods/removeAllEventListners.md)
* [AG.accelerometer.removeEventListener](methods/removeEventListener.md)
* [AG.accelerometer.startTracking](methods/startTracking.md)
* [AG.accelerometer.stopTracking](methods/stopTracking.md)

## Full example ##

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {
      window.ac_listener = AG.accelerometer.addEventListener(function(acceleration,accelerationIncludingGravity,rotationRate,interval){
        document.getElementById("accelerometer_x").innerHTML = acceleration.x;
        document.getElementById("accelerometer_y").innerHTML = acceleration.y;
        document.getElementById("accelerometer_z").innerHTML = acceleration.z;


        document.getElementById("accelerometer_ig_x").innerHTML = accelerationIncludingGravity.x;
        document.getElementById("accelerometer_ig_y").innerHTML = accelerationIncludingGravity.y;
        document.getElementById("accelerometer_ig_z").innerHTML = accelerationIncludingGravity.z;

        document.getElementById("rotation_alpha").innerHTML = rotationRate.alpha;
        document.getElementById("rotation_beta").innerHTML = rotationRate.beta;
        document.getElementById("rotation_gamma").innerHTML = rotationRate.gamma;

        document.getElementById("interval").innerHTML = interval;
      });

      document.getElementById("toggle_acc_tracking").addEventListener("click", function(e){
        e.preventDefault();
        if (AG.accelerometer.listener === null) {
          AG.accelerometer.startTracking();
        } else {
          AG.accelerometer.stopTracking();
        }
      });

      document.getElementById("remove_listener").addEventListener("click", function(e){
        e.preventDefault();
        AG.accelerometer.removeEventListener(window.ac_listener);
      });

    });
    </script>
    <style>
      td:nth-child(2){
        text-align:right;
      }
    </style>
  </head>
  <body>
  <h1>AG.accelerometer example</h1>

  <section>
    <h2>Accelerometer values:</h2>
    <p><a href="#" data-navigation="false" id="toggle_acc_tracking">Toggle</a></p>
    <table style="width:100%;">
      <tr>
        <td colspan="2"><b>acceleration:</b></td>
      </tr>
      <tr><td>x</td><td id="accelerometer_x"></td></tr>
      <tr><td>y</td><td id="accelerometer_y"></td></tr>
      <tr><td>z</td><td id="accelerometer_z"></td></tr>
      <tr>
        <td colspan="2"><b>accelerationIncludingGravity:</b></td>
      </tr>
      <tr><td>x</td><td id="accelerometer_ig_x"></td></tr>
      <tr><td>y</td><td id="accelerometer_ig_y"></td></tr>
      <tr><td>z</td><td id="accelerometer_ig_z"></td></tr>
      <tr>
        <td colspan="2"><b>rotationRate:</b></td>
      </tr>
      <tr><td>alpha</td><td id="rotation_alpha"></td></tr>
      <tr><td>beta</td><td id="rotation_beta"></td></tr>
      <tr><td>gamma</td><td id="rotation_gamma"></td></tr>
      <tr><td colspan="2"></td></tr>
      <tr>
        <td><b>interval:</b></td>
        <td id="interval"></td>
      </tr>
    </table>
    <p><a href="#" data-navigation="false" id="remove_listener">Remove listener</a></p>
  </section>
  </body>
</html>
```