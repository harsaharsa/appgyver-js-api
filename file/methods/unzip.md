# AG.file.unzip

## Summary
`unzip()` unzips a .zip file in your app's filesystem in the background.

The success callback function gets triggered after the file has been successfully unzipped. If the unzipping fails, the failure callback function gets triggered.

## Quick example:
```javascript
AG.file.unzip("Application/shared/assets/stuff.zip", "Files/", function(){
  AG.GUI.alert("Success", "File was unzipped");
});
```

## Syntax
```javascript
AG.file.unzip(filenameWithPath, toPath, successCallback, failureCallback)
```

**Parameters**

* *string* **filenameWithPath**<br>
  A string containing the filename and path of the file to be unzipped. The path is relative to the app's `views` directory.
* *string* **toPath**<br>
  A string containing the path where the file will be unzipped. The path is relative to the app's `views` directory.
* *function* **successCallback**<br>
  The success callback function.
* *function* **failureCallback**<br>
  The failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS, Android

