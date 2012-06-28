# AG.file.preview

## Summary
`preview()` previews media files in a native dialogue.

On iOS, all files are previewed with iOS's own preview dialogues.

On Android, the user is presented with a dialogue where he can choose the program to be used for the preview. The file types that can be previewed depend on the apps that are installed on the device.

The success callback function gets triggered if a suitable preview dialogue launches successfully. If the preview fails, the failure callback function gets triggered.

## Quick example:
```javascript
AG.file.preview("Application/shared/document.pdf", function(){
  AG.GUI.alert("Success", "The file was previewed.");
});
```

## Syntax
```javascript
AG.file.preview(filenameWithPath, successCallback, failureCallback)
```

**Parameters**

* *string* **filenameWithPath**<br>
  A string containing the filename and path of the file to be previewed. The path is relative to the app's `views` directory.
* *function* **successCallback**<br>
  The success callback function.
* *function* **failureCallback**<br>
  The failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS, Android

