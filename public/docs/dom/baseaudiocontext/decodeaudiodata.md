# BaseAudioContext.decodeAudioData()

The `decodeAudioData()` method of the [`BaseAudioContext`](../baseaudiocontext) Interface is used to asynchronously decode audio file data contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). In this case the `ArrayBuffer` is loaded from [`XMLHttpRequest`](../xmlhttprequest) and [`FileReader`](../filereader). The decoded [`AudioBuffer`](../audiobuffer) is resampled to the [`AudioContext`](../audiocontext)'s sampling rate, then passed to a callback or promise.

This is the preferred method of creating an audio source for Web Audio API from an audio track. This method only works on complete file data, not fragments of audio file data.

## Syntax

Older callback syntax:

    baseAudioContext.decodeAudioData(ArrayBuffer, successCallback, errorCallback);

Newer promise-based syntax:

    Promise<decodedData> baseAudioContext.decodeAudioData(ArrayBuffer);

### Parameters

ArrayBuffer  
An ArrayBuffer containing the audio data to be decoded, usually grabbed from [`XMLHttpRequest`](../xmlhttprequest), [`WindowOrWorkerGlobalScope.fetch()`](../windoworworkerglobalscope/fetch) or [`FileReader`](../filereader).

successCallback  
A callback function to be invoked when the decoding successfully finishes. The single argument to this callback is an [`AudioBuffer`](../audiobuffer) representing the decodedData (the decoded PCM audio data). Usually you'll want to put the decoded data into an [`AudioBufferSourceNode`](../audiobuffersourcenode), from which it can be played and manipulated how you want.

errorCallback  
An optional error callback, to be invoked if an error occurs when the audio data is being decoded.

### Return value

Void, or a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) object that fulfills with the decodedData.

## Example

In this section we will first cover the older callback-based system and then the newer promise-based syntax.

### Older callback syntax

In this example, the `getData()` function uses XHR to load an audio track, setting the `responseType` of the request to `arraybuffer` so that it returns an array buffer as its `response` that we then store in the `audioData` variable . We then pass this buffer into a `decodeAudioData()` function; the success callback takes the successfully decoded PCM data, puts it into an [`AudioBufferSourceNode`](../audiobuffersourcenode) created using [`AudioContext.createBufferSource()`](createbuffersource), connects the source to the [`AudioContext.destination`](destination) and sets it to loop.

The buttons in the example run `getData()` to load the track and start it playing, and stop it playing, respectively. When the `stop()` method is called on the source, the source is cleared out.

**Note**: You can [run the example live](https://mdn.github.io/webaudio-examples/decode-audio-data/) (or [view the source](https://github.com/mdn/webaudio-examples/tree/master/decode-audio-data).)

    // define variables

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var source;

    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');
    var play = document.querySelector('.play');
    var stop = document.querySelector('.stop');

    // use XHR to load an audio track, and
    // decodeAudioData to decode it and stick it in a buffer.
    // Then we put the buffer into the source

    function getData() {
      source = audioCtx.createBufferSource();
      var request = new XMLHttpRequest();

      request.open('GET', 'viper.ogg', true);

      request.responseType = 'arraybuffer';

      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
            source.buffer = buffer;

            source.connect(audioCtx.destination);
            source.loop = true;
          },

          function(e){ console.log("Error with decoding audio data" + e.err); });

      }

      request.send();
    }

    // wire up buttons to stop and play audio

    play.onclick = function() {
      getData();
      source.start(0);
      play.setAttribute('disabled', 'disabled');
    }

    stop.onclick = function() {
      source.stop(0);
      play.removeAttribute('disabled');
    }

    // dump script to pre element

    pre.innerHTML = myScript.innerHTML;

### New promise-based syntax

    ctx.decodeAudioData(audioData).then(function(decodedData) {
     // use the decoded data here
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-decodeaudiodata">Web Audio API<br />
<span class="small">The definition of 'decodeAudioData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`decodeAudioData`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`promise_syntax`

49

≤79

36

No

Yes

No

49

49

36

?

No

5.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/decodeAudioData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/decodeAudioData</a>
