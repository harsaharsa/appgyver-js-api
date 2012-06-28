# AG.device.takeScreenshot

## Summary
`takeScreenshot()` captures what is currently drawn on the device's viewport.

The success callback function is triggered if the screenshot was successfully taken. If not, the failure callback function is triggered.

## Quick example:
```javascript
AG.device.takeScreenshot(function(obj){
    var img = document.createElement("img");
    img.src = obj.screenshot;
    document.body.appendChild(img);
});
```

## Syntax
```javascript
AG.device.takeScreenshot(successCallback(data), failureCallback)
```

**Parameters**

* *function* **successCallback**<br>
  The success callback function gets an object as a callback parameter:
        * *object* **obj**<br>
        The object contains the screenshot data in a property:
            * *string* **screenshot**<br>
                The screenshot data, as a Base64-encoded string.

* *function* **failureCallback**<br>
  Failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS