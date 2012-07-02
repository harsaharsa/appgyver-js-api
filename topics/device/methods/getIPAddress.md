# AG.device.getUDID

## Summary
`getUDID()` retrieves the device's current IP address.

The success callback function is triggered if the IP was successfully retrieved. If not, the failure callback function is triggered.

## Quick example:
```javascript
AG.device.getUDID(function(obj){
    AG.GUI.alert("Your IP address is", obj.ipAddress);
});
```

## Syntax
```javascript
AG.device.getUDID(successCallback(obj), failureCallback)
```

**Parameters**

* *function* **successCallback**<br>
  The success callback function gets an object as a callback parameter:
    * *object* **obj**<br>
    The object contains the screenshot data in a property:
        * *string* **ipAddress**<br>
          A string containing the IP address of the device.

* *function* **failureCallback**<br>
  Failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS