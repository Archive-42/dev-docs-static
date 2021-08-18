SpeechSynthesisEvent.utterance
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `utterance` read-only property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface returns the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) instance that the event was triggered on.

Syntax
------

    event.utterance;

### Value

A [`SpeechSynthesisUtterance`](../speechsynthesisutterance) object.

Examples
--------

    utterThis.onpause = function(event) {
      var char = event.utterance.text.charAt(event.charIndex);
      console.log('Speech paused at character ' + event.charIndex + ' of "' +
      event.utterance.text + '", which is "' + char + '".');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisevent-utterance">Web Speech API<br />
<span class="small">The definition of 'utterance' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`utterance`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent/utterance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent/utterance</a>
