# AG.media.stopRecordingAudio

## Summary
`stopRecordingAudio()` stops an active audio recording session that was started with the `startRecordingAudio` function. If there is no audio recording session active, the method does nothing.

Audio recording is view-specific, so you must call `stopRecordingAudio` in the same view where you started recording.

## Quick example:
```javascript
AG.media.stopRecordingAudio();
```

## Syntax
```javascript
AG.media.stopRecordingAudio()
```

**Parameters**

No parameters.

## Returns
Nothing.

## Supported platforms
* iOS