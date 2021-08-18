SpeechSynthesis.paused
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `paused` read-only property of the [`SpeechSynthesis`](../speechsynthesis) interface is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if the `SpeechSynthesis` object is in a paused state, or `false` if not.

It can be set to [`paused`](pause) even if nothing is currently being spoken through it. If [`utterances`](../speechsynthesisutterance) are then added to the utterance queue, they will not be spoken until the `SpeechSynthesis` object is unpaused, using [`SpeechSynthesis.resume()`](resume).

Syntax
------

    var amIPaused = speechSynthesisInstance.paused;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Examples
--------

    var synth = window.speechSynthesis;

    synth.pause();

    var amIPaused = synth.paused; // will return true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesis-paused">Web Speech API<br />
<span class="small">The definition of 'paused' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`paused`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/paused" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/paused</a>
