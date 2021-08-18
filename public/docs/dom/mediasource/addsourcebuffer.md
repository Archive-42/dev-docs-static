# MediaSource.addSourceBuffer()

The `addSourceBuffer()` method of the [`MediaSource`](../mediasource) interface creates a new [`SourceBuffer`](../sourcebuffer) of the given [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) and adds it to the `MediaSource`'s [`sourceBuffers`](sourcebuffers) list. The new `SourceBuffer` is also returned.

## Syntax

    var sourceBuffer = mediaSource.addSourceBuffer(mimeType);

### Parameters

`mimeType`  
A [`DOMString`](../domstring) specifying the MIME type of the [`SourceBuffer`](../sourcebuffer) to create and add to the [`MediaSource`](../mediasource).

### Return value

A [`SourceBuffer`](../sourcebuffer) object representing the new source buffer that has been created and added to the media source.

### Exceptions

`InvalidAccessError`  
The value specified for `mimeType` is an empty string rather than a valid MIME type.

`InvalidStateError`  
The [`MediaSource`](../mediasource) is not in the `"open"` [`readyState`](readystate).

`NotSupportedError`  
The specified `mimeType` isn't supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), or is not compatible with the MIME types of other [`SourceBuffer`](../sourcebuffer) objects that are already included in the media source's [`sourceBuffers`](sourcebuffers) list.

`QuotaExceededError`  
The user agent can't handle any more `SourceBuffer` objects, or creating a new `SourceBuffer` using the given `mimeType` would result in an [unsupported configuration of `SourceBuffer`s](https://w3c.github.io/media-source/#sourcebuffer-configuration).

## Example

The following snippet is from a simple example written by Nick Desaulniers ([view the full demo live](https://nickdesaulniers.github.io/netfix/demo/bufferAll.html), or [download the source](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html) for further investigation.)

    var assetURL = 'frag_bunny.mp4';
    // Need to be specific for Blink regarding codecs
    // ./mp4info frag_bunny.mp4 | grep Codec
    var mimeCodec = 'video/mp4; codecs="avc1.42E01E, mp4a.40.2"';

    if ('MediaSource' in window && MediaSource.isTypeSupported(mimeCodec)) {
      var mediaSource = new MediaSource;
      //console.log(mediaSource.readyState); // closed
      video.src = URL.createObjectURL(mediaSource);
      mediaSource.addEventListener('sourceopen', sourceOpen);
    } else {
      console.error('Unsupported MIME type or codec: ', mimeCodec);
    }

    function sourceOpen (_) {
      //console.log(this.readyState); // open
      var mediaSource = this;
      var sourceBuffer = mediaSource.addSourceBuffer(mimeCodec);
      fetchAB(assetURL, function (buf) {
        sourceBuffer.addEventListener('updateend', function (_) {
          mediaSource.endOfStream();
          video.play();
          //console.log(mediaSource.readyState); // ended
        });
        sourceBuffer.appendBuffer(buf);
      });
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-mediasource-addsourcebuffer">Media Source Extensions<br />
<span class="small">The definition of 'addSourceBuffer()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`addSourceBuffer`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

## See also

- [`SourceBuffer`](../sourcebuffer)
- [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/addSourceBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/addSourceBuffer</a>
