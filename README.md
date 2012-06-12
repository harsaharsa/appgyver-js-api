# Official appgyver.js API documentation.

Appgyver.js is a JavaScript library used to access native features of your mobile device in your HTML5-based app. Think of it as a bridge between your application's HTML documents and your mobile device's hardware and proprietary software. Appgyver.js also provides you with some non-hardware related features, such as native GUI elements and transitions, useful abstractions of commonly used functions such as XMLHttpRequestsm and more.

## appgyver.js core explained

The appgyver.js core enables the communication channel between the developer's JavaScript code and the mobile device's functions. Once the DOM content of an HTML document in your app is loaded, appgyver.js core initializes and is ready to deliver messages to the device.

### Callback functions

As is common in JavaScript, many methods of the appgyver.js API take `successCallback` and `failureCallback` functions as parameters. They are resolved asynchronously in appgyver.js: the callback functions are called after the method has finished talking to the native layer (e.g. the user has finished taking a picture with the camera, the device has retrieved user location etc.), enabling you to seamlessly weave native functionalities into your app. As the names imply, the `successCallback` function is called if the API call is successful and `failureCallback` is called if the API call fails.

To explain how callback functions work, let's look at an example from the AG.geolocation API namespace.

> **Callback functions example**
>
> We can get the mobile device's current GPS coordinates with the method:
>
> `AG.geolocation.getCurrentLocation(successCallback(coords), failureCallback)` 
>
> If the native app layer fails to retrieve the current GPS coordinates, the `failureCallback` function is called. The code in the function is executed, e.g. an error message is displayed.
>
> If the native app succeeds in retrieving the GPS coordinates, the `successCallback` function is called. The data retrieved by the API call (user GPS coordinates in this case) are passed on to the successCallback function as a parameter. In this case, `coords` contains the GPS coordinates retrieved by the device. The developer is then free to do whatever they want with the data, e.g. display it to the user.

Each method's API documentation explains in more detail:
* The success and failure conditions of the API calls, i.e. what happens in the native layer.
* The type and contents of all callback parameters.

### Cross document transitions and navigation

Appgyver.js uses native animated transitions between documents and automatically maintains navigation history throughout the app. This functions in a similar way to typical browser navigation, but uses the native GUI elements instead.

The `appgyver.js` library has the navigation extension included, monitoring all clicked <a></a> tags in the HTML document.

To disable native transitions manually, use the `data-navigation="false"` data attribute in the <a></a> tag.

To disable native transitions and navigation logic for the whole project, use `appgyver.core.js` instead. You can then load the navigation extension manually by loading `appgyver.extensions.navigation.js` after `appgyver.core.js` in the HTML code.

## Topics

* [geolocation](appgyver-js-api/tree/master/geolocation/README.md)



