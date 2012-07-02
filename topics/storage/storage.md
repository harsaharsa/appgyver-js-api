# AG.storage

The **AG.storage** namespace gives access to methods that allow you to save and load persistent and temporary data using the device's filesystem. Passed data objects are automatically converted to JSON strings and back.

## Methods

* [AG.storage.get](methods/get.md)
* [AG.storage.set](methods/set.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {
      document.querySelector("button#save").addEventListener("touchstart", function(){
        var input_value = document.querySelector("input").value;
        AG.storage.set("mykey", input_value, function(){
          alert("Data was saved successfully");
        });
      });
      document.querySelector("button#load").addEventListener("touchstart", function(){
        AG.storage.get("mykey", function(key, data){
          document.querySelector("div").textContent = "Loaded data: "+data;
        }, function(){
          alert("Could not load data, perhaps  you haven't saved it yet?");
        });
      });
    }, false);
    </script>
  </head>
  <body>
    <h1>AG.storage example</h1>
    <input type="text" />
    <div></div>
    <button id="save">save</button>
    <button id="load">load</button>
 
  </body>
</html>
```