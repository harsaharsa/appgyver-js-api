# AG.media.play

## Summary
`play()` plays an audio file from the app's file system. Supported formats include .aiff, .mp3, .ogg and .wav.

Note that playing .mp3 files has a slight delay compared to .wav files due to the decoding process.

*There is currently a known issue where playing a nonexistent audio file crashes the app.*

## Quick example:
```javascript
AG.media.play("audio/myaudio.wav");
```

## Syntax
```javascript
AG.media.play(filename)
```

**Parameters**

* *string* **filename**<br>
  The filename and path of the audio file to play. The path is relative to the app's `views` directory.

## Returns
Nothing.

## Supported platforms
* iOS