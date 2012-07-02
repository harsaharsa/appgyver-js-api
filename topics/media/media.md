# AG.media

The **AG.media** namespace contains methods that allow you to record and play back audio.

## Methods
* [AG.media.play](methods/play.md)
* [AG.media.startRecordingAudio](methods/startRecordingAudio.md)
* [AG.media.stopRecordingAudio](methods/stopRecordingAudio.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
    document.addEventListener("DOMContentLoaded", function() {
      
      var startRecord = function() {
        AG.media.startRecordingAudio("myaudio");        
      }
      
      var stopRecord = function() {
        AG.media.stopRecordingAudio();
      }
      
      var play = function() {
        AG.media.play("myaudio");
      }
      
      document.querySelector("button#start_record").addEventListener("touchstart", startRecord);
      document.querySelector("button#stop_record").addEventListener("touchstart", stopRecord);
      document.querySelector("button#play").addEventListener("touchstart", play);
      
    });
    </script>
  </head>
  <body>
    <h1>AG.media example</h1>
    <button id="start_record">Start recording</button>
    <button id="stop_record">Stop recording</button>
    <button id="play">Play</button>
 
  </body>
</html>
```