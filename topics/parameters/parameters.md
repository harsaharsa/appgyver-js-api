# AG.parameters

The **AG.parameters** namespace gives access to parameters passed between HTML views. They are useful in situations when you want to pass data from one HTML document to another when transitioning between them.

Currently, the API supports query strings passed as part of an HTML link.

## Methods

* [AG.parameters.get](methods/get.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
        var msg = AG.parameters.get("msg"); 
        if (msg) AG.GUI.alert("Your parameters were:", msg);
    </script>
  </head>
  <body>
  	<h1>AG.parameter test</h1>
  	
  	<a href="index.html?msg=Hi">Say: "Hi"</a><br>
  	<a href="index.html?msg=Howdy">Say: "Howdy"</a>
  	
  </body>
</html>
```