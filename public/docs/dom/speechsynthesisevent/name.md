SpeechSynthesisEvent.name
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `name` read-only property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface returns the name associated with certain types of events occurring as the [`SpeechSynthesisUtterance.text`](../speechsynthesisutterance/text) is being spoken: the name of the [SSML](https://www.w3.org/TR/speech-synthesis/#S3.3.2) marker reached in the case of a `mark` event, or the type of boundary reached in the case of a `boundary` event.

Syntax
------

    event.name;

### Value

A [`DOMString`](../domstring).

Examples
--------

    utterThis.onboundary = function(event) {
      console.log(event.name + ' boundary reached after ' + event.elapsedTime + ' milliseconds.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisevent-name">Web Speech API<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent/name</a>
