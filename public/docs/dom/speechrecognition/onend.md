SpeechRecognition.onend
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onend` property of the [`SpeechRecognition`](../speechrecognition) interface represents an event handler that will run when the speech recognition service has disconnected (when the `end` event fires.)

Syntax
------

    mySpeechRecognition.onend = function() { ... };

Examples
--------

    var recognition = new SpeechRecognition();

    recognition.onend = function() {
      console.log('Speech recognition service disconnected');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechrecognition-onend">Web Speech API<br />
<span class="small">The definition of 'onend' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`onend`

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
-   [end event](end_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/onend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/onend</a>
