# AG.GUI.removeSplashScreen

## Summary
`removeSplashScreen()` can be used to remove the native splash screen that is shown when the application is loading. This can be useful if your application needs to wait for some assets to load, for example.

This method is not supported in Edge mode.

## Quick example:
```javascript
AG.GUI.removeSplashScreen("fade");
```

## Syntax
```javascript
AG.GUI.setTopBarImagePath(effect)
```

**Parameters**

* *string* **effect**
  The name of the effect used to remove the splash screen. Possible values are:
    * `fade`
    * `slideFromLeft`
    * `slideFromRight`

## Returns
Nothing.

## Supported platforms
* iOS