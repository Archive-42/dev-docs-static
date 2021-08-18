SpeechSynthesis.pending
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `pending` read-only property of the [`SpeechSynthesis`](../speechsynthesis) interface is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if the utterance queue contains as-yet-unspoken utterances.

Syntax
------

    var amIPending = speechSynthesisInstance.pending;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Examples
--------

    var synth = window.speechSynthesis;

    var utterance1 = new SpeechSynthesisUtterance('How about we say this now? This is quite a long sentence to say.');
    var utterance2 = new SpeechSynthesisUtterance('We should say another sentence too, just to be on the safe side.');

    synth.speak(utterance1);
    synth.speak(utterance2);

    var amIPending = synth.pending; // will return true if utterance 1 is still being spoken and utterance 2 is in the queue

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesis-pending">Web Speech API<br />
<span class="small">The definition of 'pending' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`pending`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/pending" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/pending</a>
