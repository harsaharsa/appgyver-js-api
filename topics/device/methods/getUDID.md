# AG.device.getUDID

## Summary
`getUDID()` retrieves the device's Unique Device Identifier (UDID).

The success callback function is triggered if the UDID was successfully retrieved. If not, the failure callback function is triggered.

## Quick example:
```javascript
AG.device.getUDID(function(udid){
    AG.GUI.alert("Your UDID is", udid);
});
```

## Syntax
```javascript
AG.device.getUDID(successCallback(udid), failureCallback)
```

**Parameters**

* *function* **successCallback**<br>
  The success callback function gets the device UDID as a callback parameter:
        * *string* **udid**<br>
        A string containing the device's UDID.

* *function* **failureCallback**<br>
  Failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS