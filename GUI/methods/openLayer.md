# AG.GUI.openLayer

## Summary
`openLayer()` opens the target document in a new view that exists as a separate layer on top of the original view. The original view remains active under the new layer.

By default, the new layer includes a native back button that will close the layer and return to the original view.

This method is currently supported in Edge mode only.

## Quick example:
```javascript
AG.GUI.openLayer("second_level/index.html")
```

## Syntax
```javascript
AG.GUI.openLayer(location)
```

**Parameters**

* *string* **location**
  The local URL pointing to the HTML document that will be opened on the new layer.

## Returns
Nothing.

## Supported platforms
* iOS