# AG.events

The **AG.events** namespace gives access to various event listeners that get fired when specific conditions are met. These event listeners are view-specific, meaning that an event listener added to one view won't get fired in another and so on.

### Edge mode notes

Currently, `focus` has extended functionality in Edge mode (e.g. registering going to the home screen and back) and `lostFocus` only works in Edge mode.

## Methods

* [AG.events.addEventListener](methods/addEventListener.md)
* [AG.events.removeAllEventListeners](methods/removeAllEventListeners.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
        document.addEventListener("DOMContentLoaded", function(){          
          
          var buttons = document.querySelectorAll("button");;
          
          for (var i = 0; i < buttons.length; i++) {
            buttons[i].addEventListener("touchstart", function() {
              
              var lst = this.getAttribute("data-listener");
              
              if (lst != "removeAll") {  
                AG.events.addEventListener(lst, function () {
                  AG.GUI.alert("Event listener fired", lst);
                });
                AG.GUI.alert("Event listener added:", lst);
                
              } else {                
                AG.events.removeAllEventListeners();
                AG.GUI.alert("All event listeners removed!");                
              }

            });
          }
        }, false);
    </script>
  </head>
  <body>
    <h1>AG.events example</h2>
      
    <button data-listener="topDoubleTapped">Add topDoubleTapped listener</button><br>
    <button data-listener="focus">Add focus listener</button><br>
    <button data-listener="lostFocus">Add lostFocus listener (Edge mode only)</button><br>
    <br>
    <br>
    <button data-listener="removeAll">Remove all event listeners</button>
  </body>
</html>
```