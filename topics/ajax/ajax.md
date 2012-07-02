# AG.ajax

The **AG.ajax** namespace contains methods that abstract the common XMLHttpRequest flow. This means you are not forced to write the basic XMLHttpRequest abstraction by yourself, or to use a third party JavaScript library just to get basic AJAX requests working.

By default, the AJAX extension is configured to use the "GET" http method and ask for JSON data.

## Methods
* [AG.ajax.send](methods/send.md)

## Full example

```javascript
var myXMLHttpRequest = AG.ajax.send("http://my_json_location.json", {
  success: function(data){
    alert(data);
  },
  failure: function(status, request){
    alert("XHR failed, status: "+status);
  }
});
```