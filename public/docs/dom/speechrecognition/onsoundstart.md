SpeechRecognition.onsoundstart
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onsoundstart` property of the [`SpeechRecognition`](../speechrecognition) interface represents an event handler that will run when any sound — recognisable speech or not — has been detected (when the [soundstart event](soundstart_event) fires.)

Syntax
------

    mySpeechRecognition.onsoundstart = function() { ... };

Examples
--------

    recognition.onsoundstart = function() {
      console.log('Some sound is being received');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechrecognition-onsoundstart">Web Speech API<br />
<span class="small">The definition of 'onsoundstart' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`onsoundstart`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/onsoundstart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/onsoundstart</a>
