SpeechRecognition: audiostart event
===================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `audiostart` event of the [Web Speech API](../web_speech_api) is fired when the user agent has started to capture audio for speech recognition.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onaudiostart"><code>onaudiostart</code></a></td></tr></tbody></table>

Examples
--------

You can use the `audiostart` event in an [`onaudiostart`](onaudiostart) method:

    var recognition = new webkitSpeechRecognition() || new SpeechRecognition();

    recognition.addEventListener('audiostart', function() {
      console.log('Audio capturing started');
    });

Or use the [onaudiostart](onaudiostart) event handler property:

    recognition.onaudiostart = function() {
      console.log('Audio capturing started');
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

`audiostart_event`

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
-   [`onaudiostart`](onaudiostart) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/audiostart_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/audiostart_event</a>
