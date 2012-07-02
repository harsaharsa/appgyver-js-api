# AG.ajax.send

## Summary
`send()` sends an XMLHttpRequest with the given parameters, and then executes a success or failure callback function with the returned data available as a parameter object.

## Quick example:
```javascript
	var myXMLHttpRequest = AG.ajax.send("http://my_json_location.json", {
      success: function(data){
        AG.GUI.alert(data);
      },
      failure: function(status, request){
        AG.GUI.alert("XHR failed, status: "+status);
      }
    });
```

## Syntax
```javascript
AG.ajax.send(url, options);
```

**Parameters**

* *string* **url**<br>
  A string containing the URL the HTTP request is sent to.
  
* *object* **options**<br>
  A JSON object containing the possible options for the request. The object has the following fields:
  
    * *string* **type**<br>
    The type of the HTTP request. The default value is `GET`.
    
    * *object* **headers**<br>
    A JSON object containing the headers for the request. Contains the fields:
    
        * *string* **"Content-Type"**<br>
        The Content-Type header of the XMLHttpRequest. The default value is `application/json`.
        
        * *string* **"Accepts"**<br>
        The Accepts header of the XMLHttpRequest. The default value is `application/json, text/javascript, text/plain, text/html, */*`
        
    * *function* **success**<br>
    The success callback function.
    
    * *function* **failure**<br>
    The failure callback function.

## Returns 

The requested object.

## Supported platforms
* iOS