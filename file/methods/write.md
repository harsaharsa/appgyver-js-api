# AG.file.write

## Summary
`write()` creates or overwrites files in the app's file system.

The success callback function gets triggered if the file is created successfully, or an existing file is overwritten. Otherwise, the failure callback function gets triggered.

## Quick example:
```javascript
AG.file.write("Files/index.html", "<html><body>Hello from new file!</body></html>", function(){
  AG.GUI.alert("Success", "The file was created!");
});
```

## Syntax
```javascript
AG.file.write(toFile, content, successCallback, failureCallback)
```

**Parameters**

* *string* **toFile**<br>
  A string containing the filename and path of the file to be created. The path is relative to the app's `views` directory.
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

