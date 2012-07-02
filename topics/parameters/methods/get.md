# AG.parameters.get

## Summary
`get()` allows you pass parameters between HTML documents.

When you are developing an application that needs to pass parameters to other views (i.e. other HTML documents), you can pass them as query strings in an URL link and then use this function to access the field-value pairs.

The field-value pairs are inputted after a question mark in the URL, e.g. `"second.html?msg=hello"`.

## Quick example:
```javascript
var passed_parameter = AG.parameters.get("field_name");
```

## Syntax
```javascript
AG.parameters.get(field_name);
```

**Parameters**

* *function* **field_name**<br>
  The name of the field in a field-value pair that was passed as part of a query string in the linked URL.

  E.g. if the URL that was linked is `"second_page.html?msg=hello"`, `"msg"` would be a proper `field_name` parameter for the function.

## Returns 

*string*
Contains the value matching the field string given as a parameter. E.g. if the URL is `"second.html?msg=hello"`, `AG.parameters.get("msg")` returns `"hello"`.

## Supported platforms
* iOS