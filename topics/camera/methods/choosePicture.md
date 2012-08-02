# AG.camera.choosePicture

## Summary
`choosePicture()` shows the user a native dialogue for selecting an image source: taking a new picture with the camera or choosing one from the device's photo library.

The success callback function gets triggered when the user successfully selects an image (either a new one or an existing one). The failure callback function gets triggered if 

* taking the picture fails, 
* retrieving the picture from the native photo library fails, or 
* the user cancels the native dialogue. 

If the device does not have a camera, the method will try to open the device's photo library instead, bypassing the dialogue for selecting an image source.

## Quick example:
```javascript
camera.choosePicture({filename: "myFile.jpg"}, successCallback(data), failureCallback);
```

## Syntax
```javascript
camera.choosePicture(options, successCallback(data), failureCallback);
```

**Parameters**

* *JSON* **options**<br>
  A JSON object containing the options for the method call as key-value pairs:
    * *filename* **string**<br>
        The filename for the captured image.
    * *title* **string** (optional)<br>
        The title of the native dialogue for selecting an image source. The default value is `"Select source"`
    * *cancel_button* **string** (optional)<br>
        In the native dialogue, the text of the cancel button. The default value is `"Cancel"`.
    * *camera_button* **string** (optional)<br>
        In the native dialogue, the text of the button for opening the device's camera. The default value is `"Open Camera"`.
    * *library_button* **string** (optional)<br>
        In the native dialogue, the text of the button for accessing the device's photo library. The default value is `"Choose From Library"`.
    
* *function* **successCallback**<br>
  The success callback receives a parameter object from the native layer:
    * *object* **data**<br>
        An object containing the captured image's file path, stored in the property:
      * *string* **imagePath**<br>
          A string containing the path of the captured image in the device's file system.

* *function* **failureCallback**<br>
    The failure callback function.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS, Android