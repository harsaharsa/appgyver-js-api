# AG.camera.takeVideo

## Summary
`takeVideo()` shows the user the native screen for taking a video with the device's camera. The video clip is then saved to a file in the file system.

The success callback function is triggered after the user has successfully taken a video clip. The failure callback function is triggered if taking the video fails, if the user cancels the native camera dialogue or if the device does not have a camera.

## Quick example:
```javascript
AG.camera.takeVideo(filename, successCallback(data), failureCallback);
```

## Syntax
```javascript
AG.camera.takeVideo(filename, successCallback(data), failureCallback)
```

**Parameters**

* *string* **filename**<br>
  The filename for the video clip taken by the camera.
  
* *function* **successCallback**<br>
  The success callback function receives a parameter object from the native layer:
    * *object* **data**<br>
        An object containing the captured video's file path, stored in the property:
        * *string* **videoPath**<br>
            A string containing the path of the captured image in the device's file system.

* *function* **failureCallback**<br>
  Failure callback function.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS