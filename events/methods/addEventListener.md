# AG.events.addEventListener

## Summary
`addEventListener()` adds an event listener to the current view that listens for the specified event. The available events and their functions are slightly different between normal mode and Edge mode:

**Normal mode events:**

* **focus**<br>
 Happens when the current tab bar view gains focus (after switching to another tab).
* **topDoubleTapped**<br>
 Happens when the user double-taps the navigation bar.

**Edge mode events:**

* **focus**<br>
 Happens when the current view gains focus (after returning from another view or after going to home screen and back).
* **lostFocus**<br>
 Happens when navigation bar back navigation button is tapped.

The success callback function of the event listener is fired every time the listened event happens.

## Quick example:
```javascript
AG.events.addEventListener("topDoubleTapped", function(){
  AG.GUI.alert("Success", "Top bar was double tapped!");
});
```

## Syntax
```javascript
AG.events.addEventListener(event, successCallback)
```

**Parameters**

* *string* **event**<br>
  The event that the event listener listens to. Possible values are:
    * `"focus"`
    * `"topDoubleTapped"`
    * `"lostFocus"`
    See above for more details on when the different events are triggered.
    
* *function* **successCallback**<br>
  The success callback function.

## Returns

Nothing.

## Supported platforms
* iOS, Android (Edge mode events only)