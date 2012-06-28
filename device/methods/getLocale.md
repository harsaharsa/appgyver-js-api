# AG.device.getLocale

## Summary
`getLocale()` retrieves the device's locale settings.

The success callback function is triggered if the locale settings were successfully retrieved. If not, the failure callback function is triggered.

## Quick example:
```javascript
AG.device.getLocale(function(data)){
    AG.GUI.alert("Your locale data is", JSON.stringify(data));
});
```

## Syntax
```javascript
AG.device.getLocale(successCallback(data), failureCallback)
```

**Parameters**

* *function* **successCallback**<br>
  The success callback function gets the device UDID as a callback parameter:
    * *JSON* **data**<br>
        A JSON object containing the locale information as key-value pairs, with the following keys (all *string*s):
        * localeIdentifier
        * languageCode
        * countryCode
        * measurementSystem
        * decimalSeparator
        * groupingSeparator
        * currencySymbol
        * currencyCode

            In iOS, the object contains additional keys not available on Android:
        * collatorIdentifier 
        * quotationBeginDelimiter
        * quotationEndDelimiter
        * alternateQuotationBeginDelimiter
        * alternateQuotationEndDelimiter
        * calendar

* *function* **failureCallback**<br>
  Failure callback function.
  
## Native layer details, iOS

The native layer gets most of the locale information from the `NSLocale` class. Calendar information is retrieved from the `NSCalendar` class. It then creates a JSON object with the key-value pairs for the locale data and passes it to the JavaScript API.

## Returns
[AG.Deferred()](../../Deferred/Deferred.md)

## Supported platforms
* iOS, Android