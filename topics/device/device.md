# AG.device #

The **AG.device** namespace contains methods that give access to device-specific information, including the current contents of the screen.

## Methods ##

* [AG.device.getUDID](methods/getUDID.md)
* [AG.device.takeScreenshot](methods/takeScreenshot.md)
* [AG.device.getLocale](methods/getLocale.md)
* [AG.device.getIPAddress](methods/getIPAddress.md)

## Full example ##

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function(){

      // device.getUDID
      document.getElementById("getUDID").addEventListener("touchstart", function(){
        AG.device.getUDID(
          // successCallback
          function(udid){
            AG.GUI.alert("Device UDID: ", udid);
          },
          // failureCallback
          function(){
            AG.GUI.alert("Could not get device UDID");
          });
      });

      // device.getIPAddress
      document.getElementById("getIP").addEventListener("touchstart", function(){
        AG.device.getIPAddress(
          // successCallback
          function(obj){
            AG.GUI.alert("Device IP: ", obj.ipAddress);
          },
          // failureCallback
          function(){
            AG.GUI.alert("Could not get device IP");
          });
      });

      // device.takeScreenshot
      document.getElementById("takeScreenshot").addEventListener("touchstart", function(){
        AG.device.takeScreenshot(
          // successCallback
          function(obj){
            var img = document.createElement("img");
            img.src = obj.screenshot;
            document.body.appendChild(img);
          },
          // failureCallback
          function(){
            AG.GUI.alert("Could not take screenshot");
          });
      });

      // device.getLocale
      document.getElementById("getLocale").addEventListener("touchstart", function(){
        AG.device.getLocale(
          // successCallback
          function(data){
          AG.GUI.alert("Locale data:", JSON.stringify(data));
          },
          // failureCallback
          function(){
            AG.GUI.alert("Could not get locale data")
          });
      });

    }, false);
    </script>
  </head>
  <body>
    <h1>AG.device examples</h1>
    <button id="getUDID">Get device's UDID</button><br /><br />
    <button id="getIP">Get device's IP</button><br /><br />
    <button id="getLocale">Get device's locale data</button><br /><br />
    <button id="takeScreenshot">Take screenshot</button><br /><br />
  </body>
</html>
```