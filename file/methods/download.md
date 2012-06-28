# AG.file.download

## Summary
`download()` download a remote file to your application's directory.

The success callback function gets triggered if the file download is successful. If not, the failure callback function gets triggered.

## Quick example:
```javascript
AG.file.download("Files/laptop.png", "http://www.appgyver.com/images/laptop.png", function(){
  AG.GUI.alert("Success", "The file was downloaded!");
});
```

## Syntax
```javascript
AG.file.download(toFile, url, successCallback, failureCallback)
```

**Parameters**

* *string* **toFile**<br>
  A string containing the filename and path where the downloaded file will be saved. The path is relative to the app's `views` directory.
* *string* **url**<br>
  The remote URL where the file will be downloaded from
* *function* **successCallback**<br>
  The success callback function.
* *function* **failureCallback**<br>
  The failure callback function.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS, Android

