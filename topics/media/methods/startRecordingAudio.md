# AG.media.startRecordingAudio

## Summary
`startRecordingAudio()` starts recording audio via the device's microphone. You must call `stopRecordingAudio` to complete the recording. 

Audio recording is view-specific, so you must call `stopRecordingAudio` in the same view where you started recording.

## Quick example:
```javascript
AG.media.startRecordingAudio("audio/myaudio.wav");
```

## Syntax
```javascript
AG.media.startRecordingAudio(filename)
```

**Parameters**

* *string* **filename**<br>
  The filename and path of where the recorded audio file will be stored. The path is relative to the app's `views` directory. Existing files with the same name will be overwritten.

## Returns
Nothing.

## Supported platforms
* iOS