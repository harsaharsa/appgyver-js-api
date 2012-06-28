# AG.storage.get

## Summary
`get()` lets you load data that was saved using `AG.storage.set` function.

The loaded data is automatically parsed from JSON to a JS object.

The success callback function gets triggered if the data matching the key was retrieved successfully. Otherwise, the failure callback function gets triggered.

## Quick example:
```javascript
AG.storage.get("mykey", function(key, data){
  AG.GUI.alert("Loaded data", data);
});
```

## Syntax
```javascript
AG.storage.get(key, successCallback(key, data), failureCallback);
```

**Parameters**

* *string* **key**<br>
  The key for the data that is to be retreived.
* *function* **successCallback**<br>
  The success callback function has the following parameter objects:
    * *string* **key**<br>
     The key that was used to retrieve the data.
    * *object* **data**<br>
     The data that was retrieved. The stored JSON is automatically parsed to a JS object.
  
* *function* **failureCallback**<br>
  The failure callback function.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS