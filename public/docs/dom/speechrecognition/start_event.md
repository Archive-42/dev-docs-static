SpeechRecognition: start event
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `start` event of the [Web Speech API](../web_speech_api) [`SpeechRecognition`](../speechrecognition) object is fired when the speech recognition service has begun listening to incoming audio with intent to recognize grammars associated with the current `SpeechRecognition`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onstart</code></td></tr></tbody></table>

Examples
--------

You can use the `start` event in an `addEventListener` method:

    var recognition = new webkitSpeechRecognition() || new SpeechRecognition();

    recognition.addEventListener('start', function() {
      console.log('Speech recognition service has started');
    });

Or use the `onstart` event handler property:

    recognition.onstart = function() {
      console.log('Speech recognition service has started');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechreco-events">Web Speech API<br />
<span class="small">The definition of 'speech recognition events' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`start_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/start_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/start_event</a>
