MediaError.message
==================

The read-only property `MediaError.message` returns a [`DOMString`](../domstring) which contains a human-readable string offering specific diagnostic details related to the error described by the `MediaError` object, or an empty string (`""`) if no diagnostic information can be determined or provided.

Syntax
------

    var errorMessage = mediaError.message;

### Value

A [`DOMString`](../domstring) providing a detailed, specific explanation of what went wrong and possibly how it might be fixed. This is *not* a generic description of the [`MediaError.code`](code) property's value, but instead goes deeper into the specifics of this particular error and its circumstances. If no specific details are available, this string is empty.

Example
-------

This example creates a [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element, establishes an error handler for it, then lets the user click buttons to choose whether to assign a valid audio file or a missing file to the element's [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio#attr-src) attribute. The error handler outputs a message to a box onscreen describing the error, including both the `code` and the `message`.

Only the relevant parts of the code are displayed; you can [see the complete source code here](https://github.com/mdn/dom-examples/blob/master/media/mediaerror/).

The example creates an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element and lets the user assign either a valid music file to it, or a link to a file which doesn't exist. This lets us see the behavior of the `error` event handler, which is received by an event handler we add to the `<audio>` element itself.

The error handler looks like this:

      audioElement.onerror = function() {
        let s = "";
        let err = audioElement.error;

        switch(err.code) {
          case MediaError.MEDIA_ERR_ABORTED:
            s += "The user canceled the audio.";
            break;
          case MediaError.MEDIA_ERR_NETWORK:
            s+= "A network error occurred while fetching the audio.";
            break;
          case MediaError.MEDIA_ERR_DECODE:
            s+= "An error occurred while decoding the audio.";
            break;
          case MediaError.MEDIA_ERR_SRC_NOT_SUPPORTED:
            s+= "The audio is missing or is in a format not supported by your browser.";
            break;
          default:
            s += "An unknown error occurred.";
            break;
        }

        let message = err.message;

        if (message && message.length) {
          s += " " + message;
        }

        displayErrorMessage("<strong>Error " + err.code + ":</strong> " + s + "<br>");
      };

This gets the [`MediaError`](../mediaerror) object describing the error from the [`error`](../htmlmediaelement/error) property on the [`HTMLAudioElement`](../htmlaudioelement) representing the audio player. The error's [`code`](code) attribute is checked to determine a generic error message to display, and, if `message` is not empty, it's appended to provide additional details. Then the resulting text is output to the log.

### Result

You can try out this example below, and can [see the example in action outside this page here](https://mdn.github.io/dom-examples/media/mediaerror/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-mediaerror-message">HTML Living Standard<br />
<span class="small">The definition of 'MediaError.message' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`message`

59

79

52

No

46

No

59

59

52

43

No

7.0

See also
--------

-   [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) and [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
-   The interface defining it, [`MediaError`](../mediaerror).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaError/message" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaError/message</a>
