# AG.storage.set

## Summary
`set()` lets you save data to the device's filesystem. You can then retrieve them with `AG.storage.get`.

The data is converted to a JSON string upon saving. Existing data with the same key is overwritten.

The success callback function gets triggered if the data was saved successfully. Otherwise, the failure callback function gets triggered.

## Quick example:
```javascript
AG.storage.set("mykey", "some data", function(){
  AG.GUI.alert("Data was saved successfully");
});```

## Syntax
```javascript
AG.storage.set(key, data, successCallback, failureCallback);
```

**Parameters**

* *string* **key**<br>
  The key for the data that is to be saved.
* *integer* or *object* or *string* ***data** (anything that is a proper parameter for `JSON.stringify`)
  The data to be saved.
* *function* **successCallback**<br>
  The success callback function.
* *function* **failureCallback**<br>
  The failure callback function.

## Returns 
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS