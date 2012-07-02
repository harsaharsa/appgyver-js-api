# AG.navigation.setHistory

## Summary
`setHistory()` saves the given history array (an array of file paths) to the current view's navigation history array.

The history array is saved to remote storage as a temporary document, which means it will be removed on application restart.

The returned Deferred object is resolved when the history array is successfully saved.

## Quick example:
```javascript
var deferred = AG.navigation.setHistory(["myfeature/index.html", "myfeature/show.html"]);

deferred.done(function(history){
  AG.GUI.alert("This is your history now: " + JSON.stringify(history));
});
```

## Syntax
```javascript
AG.navigation.setHistory(history_array)
```

**Parameters**

* *array of strings* **history_array**<br>
  An array of strings containing the file paths of HTML documents. The array will be stored in the current view's navigation history array.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS