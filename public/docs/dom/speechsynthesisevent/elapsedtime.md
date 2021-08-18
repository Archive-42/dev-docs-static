SpeechSynthesisEvent.elapsedTime
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `elapsedTime` read-only property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface returns the elapsed time in seconds after the [`SpeechSynthesisUtterance.text`](../speechsynthesisutterance/text) started being spoken that the event was triggered at.

Syntax
------

    event.elapsedTime;

### Value

A float.

Examples
--------

    utterThis.onboundary = function(event) {
      console.log(event.name + ' boundary reached after ' + event.elapsedTime + ' seconds.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisevent-elapsedtime">Web Speech API<br />
<span class="small">The definition of 'elapsedTime' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`elapsedTime`

33

14

49

No

21

7

No

33

62

No

7

3.0

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent/elapsedTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent/elapsedTime</a>
