MediaSource.isTypeSupported()
=============================

The `MediaSource.isTypeSupported()` static method returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value which is `true` if the given MIME type is *likely* to be supported by the current [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent). That is, if it can successfully create [`SourceBuffer`](../sourcebuffer) objects for that MIME type. If the returned value is `false`, then the user agent is certain that it *cannot* access media of the specified format.

Syntax
------

    var isItSupported = mediaSource.isTypeSupported(mimeType);

### Parameters

`mimeType`  
The MIME media type that you want to test support for in the current browser. This may include the `codecs` parameter to provide added details about the codecs used within the file.

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the browser feels that it can *probably* play media of the specified type. This is *not* a guarantee, however, and your code must be prepared for the possibility that the media will not play correctly if at all. A value of `false` is a guarantee that media of the given type will *not* play, however.

All web APIs that work with media files use a "no/maybe/probably" approach (or, in this case, "no or probably") when determining if a media type can be used. This is because media files are complex, intricate constructs with far too many subtle variations to be absolutely certain of anything until you actually use the contents of the media.

Example
-------

The following snippet is from an example written by Nick Desaulniers ([view the full demo live](https://nickdesaulniers.github.io/netfix/demo/bufferAll.html), or [download the source](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html) for further investigation.)

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-mediasource-istypesupported">Media Source Extensions<br />
<span class="small">The definition of 'isTypeSupported()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`isTypeSupported`

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

8

1.5

See also
--------

-   [Media Source Extensions API](../media_source_extensions_api)
-   [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
-   [The "codecs" parameter in common media types](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter)
-   [`SourceBuffer`](../sourcebuffer)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/isTypeSupported" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/isTypeSupported</a>
