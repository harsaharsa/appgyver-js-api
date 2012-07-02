# AG.navigation.addToHistory

## Summary
`addToHistory()` adds a given location (HTML file path) to the current view's navigation history array.

The returned Deferred object is resolved when the location has been added to the navigation history array.

[AG.navigation.getHistory](getHistory.md) and [AG.navigation.setHistory](setHistory.md) are used internally to maintain the navigation history array.

## Quick example:
```javascript
var deferred = AG.navigation.addToHistory("myfeature/index.html");

deferred.done(function(history){
  AG.GUI.alert("Success", "This is your history now: " + JSON.stringify(history));
});
```

## Syntax
```javascript
AG.navigation.addToHistory(location)
```

**Parameters**

* *string* **location**<br>
  Location that will be added to the current view's navigation history array.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS