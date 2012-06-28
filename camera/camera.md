# AG.camera #

The **AG.camera** namespace contains methods that give access to the mobile device's camera, allowing you to capture pictures and video.

## Methods ##
* [AG.camera.choosePicture](methods/choosePicture.md)
* [AG.camera.flashOn](methods/flashOn.md)
* [AG.camera.flashOff](methods/flashOff.md)
* [AG.camera.takePicture](methods/takePicture.md)
* [AG.camera.takeVideo](methods/takeVideo.md)
* [AG.camera.toggleFlash](methods/toggleFlash.md)

## Full example ##

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {
      var media = document.getElementById("media");

      document.getElementById("take_picture").addEventListener("touchstart", function(){
        var unique_file_name = "" + (new Date()).getTime() + "_pic.jpg";
        var success = function(data){
          var img = document.createElement("img");
          img.src = data.imagePath;
          img.style.width = "150px";
          img.style.height = "150px;";
          media.appendChild(img);
        };
        var failure = function(){
          alert("User did not take picture");
        };
        AG.camera.takePicture(unique_file_name, success, failure);
      });

      document.getElementById("record_video").addEventListener("touchstart", function(){
        var unique_file_name = "" + (new Date()).getTime() + "_pic.mp4";
        var success = function(data){
          var video = document.createElement("video");
          video.src = data.moviePath;
          video.style.width = "150px";
          video.style.height = "150px;";
          media.appendChild(video);
        };
        var failure = function(){
          alert("User did not record video");
        };
        AG.camera.takeVideo(unique_file_name, success, failure);
      });
    }, false);
    </script>
  </head>
  <body>
    <h1>AG.camera example</h1>

    <a href="#" id="take_picture" data-navigation="false">Take Picture</a>
    <a href="#" id="record_video" data-navigation="false">Record a Video</a>
    <div id="media"></div>

  </body>
</html>
```