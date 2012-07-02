# AG.camera.flashOff

## Summary
`flashOff()` switches the flash LED of the device's camera off.

The success callback function is triggered if the flash LED is successfully turned off.

The failure callback function is triggered if the flash LED is already off, or the device does not have a camera flash LED.

## Quick example:
```javascript
AG.camera.flashOff();
```

## Syntax
```javascript
AG.camera.flashOff(successCallback, failureCallback)
```

**Parameters**

* *function* **successCallback**<br>
  Success callback function.
* *function* **failureCallback**<br>
  Failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS