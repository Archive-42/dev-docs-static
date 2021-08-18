SpeechRecognition.onsoundend
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onsoundend` property of the [`SpeechRecognition`](../speechrecognition) interface represents an event handler that will run when any sound — recognisable speech or not — has stopped being detected (when the `soundend` event fires.)

Syntax
------

    mySpeechRecognition.onsoundend = function() { ... };

Examples
--------

    recognition.onsoundend = function() {
      console.log('Sound has stopped being received');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechrecognition-onsoundend">Web Speech API<br />
<span class="small">The definition of 'onsoundend' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`onsoundend`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/onsoundend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/onsoundend</a>
