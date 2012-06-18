# Official appgyver.js API documentation.

Appgyver.js is a JavaScript library used to access native features of your mobile device in your HTML5-based app. Think of it as a bridge between your application's HTML documents and your mobile device's hardware and proprietary software. Appgyver.js also provides you with some non-hardware related features, such as native GUI elements and transitions, useful abstractions of commonly used functions such as XMLHttpRequests and more.

## Topics

* [AG.geolocation](http://github.com/AppGyver/appgyver-js-api/tree/master/geolocation/geolocation.md)
* [AG.compass](http://github.com/AppGyver/appgyver-js-api/tree/master/compass/README.md)

## The appgyver.js library explained

The appgyver.js JavaScript library enables the communication channel between the developer's HTML5 code and the mobile device's functions. Once the DOM content of an HTML document in your app is loaded, appgyver.js core initializes and is ready to deliver messages to the device.

In the following sections, we will go through some core features of the appgyver.js library that are shared among individual API calls, as well as detail how they interact with the native application layer.

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

Instead of giving the callback functions as parameters, you can use the appgyver.js implementation of [Deferred objects](http://github.com/AppGyver/appgyver-js-api/tree/master/Deferred/Deferred.md) to manage them. The methods that support this return an `AG.Deferred()` object.

### AppGyver views and layers

The AppGyver Client renders your app's HTML5 content in WebKit-powered windows called **views**. This means that everything that works on a WebKit-based mobile browser will work in AppGyver: all fancy CSS transitions, third-party JavaScript libraries and so on. For iOS, the WebKit renderer is the same one that is used in Mobile Safari. For Android, the renderer.

Currently, we are in the process of renewing our navigation and native GUI code, which means that Edge and normal modes have slightly different functionalities.

In **normal mode** navigation, each tab bar tab is a separate view. This means that changing between tabs leaves the original tab view intact, including all JavaScript that might be running. When you click on a link on a page, the view loads a new HTML5 page and discards the old one. If you go back to the original page e.g. via the native back button, the content is loaded from scratch. To preserve e.g. the scroll state of the original page, you should do it via separate JavaScript.

In **Edge mode** navigation, the tabs are still separate views, but by using the [`AG.GUI.openLayer`](http://github.com/AppGyver/appgyver-js-api/tree/master/GUI/openLayer.md) API call, you can open a new view on top of the current one as a "layer". The original page stays active and open under the layer, and once you click the native back button, the topmost layer is removed and the layer underneath becomes the one that is rendered. Think of it as laying down a new sheet of paper on top of the current view.

### Cross document transitions and navigation

Appgyver.js uses native animated transitions between documents and automatically maintains navigation history throughout the app. This functions in a similar way to typical browser navigation, but uses the native GUI elements instead.

The appgyver.js library has the navigation extension included by default. All `<a></a>` tags in the HTML document are monitored and native transitions are triggered automatically.

To disable native transitions manually, use the `data-navigation="false"` data attribute in the link tag: `<a data-navigation="false", href="myLink.html">link</a>`

To disable native transitions and navigation logic for the whole project, use the appgyver.core.js library instead. If you want, you can then load the navigation extension manually by loading appgyver.extensions.navigation.js after appgyver.core.js in the HTML code.