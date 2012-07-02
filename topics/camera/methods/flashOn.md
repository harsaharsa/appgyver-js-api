# AG.camera.flashOn

## Summary
`flashOn()` switches the flash LED of the device's camera on. 

The success callback function is triggered if the flash LED is successfully turned on.

The failure callback function is triggered if the flash LED is already on, or the device does not have a camera flash LED.

## Quick example:
```javascript
AG.camera.flashOn();
```

## Syntax
```javascript
AG.camera.flashOn(successCallback, failureCallback)
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