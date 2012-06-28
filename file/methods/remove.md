# AG.file.remove

## Summary
`remove()` removes a file or directory from the app's file system.

The success callback function gets triggered if the file or directory is removed successfully. Otherwise, the failure callback function gets triggered.

## Quick example:
```javascript
AG.file.write("Files/uselessFile.png", function() {
  AG.GUI.alert("Success", "The file was created!");
});
```

## Syntax
```javascript
AG.file.write(target, successCallback, failureCallback)
```

**Parameters**

* *string* **target**<br>
  A string containing the target file or directory that will be removed. The path is relative to the app's `views` directory.
* *string* **content**<br>
  A string of data that will be written into the file.
* *function* **successCallback**<br>
  The success callback function.
* *function* **failureCallback**<br>
  The failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS

