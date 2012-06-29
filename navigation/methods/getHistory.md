# AG.navigation.getHistory

## Summary
`getHistory()` retrieves the current view's navigation history array (an array of file paths) from remote storage. History arrays are saved as temporary documents, which means they will be removed on application restart.
 
The returned Deferred Object is resolved when the history array has been retrieved.
 
If the history document does not exist, empty array is returned.

## Quick example:
```javascript
var deferred = AG.navigation.getHistory();

deferred.done(function(history_document_key, history_document){
  AG.GUI.alert("Success", "Your history document " + history_document_key + " is now: " JSON.stringify(history_document);
});
```

## Syntax
```javascript
AG.navigation.getHistory()
```

**Parameters**

* *array of strings* **history_array**<br>
  An array of strings containing the file paths of HTML documents. The array will be stored in the current view's navigation history array.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

The Deferred object is resolved with the following arguments:

* *string* **history_document_key**<br>
  The key that was used to retrieve the history array document.
* *array of strings* **history_document**<br>
  An array containing the navigation history. If the history document does not exist, this argument points to an empty array.

## Supported platforms
* iOS