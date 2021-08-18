SpeechSynthesis.pause()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `pause()` method of the [`SpeechSynthesis`](../speechsynthesis) interface puts the `SpeechSynthesis` object into a paused state.

Syntax
------

    speechSynthesisInstance.pause();

### Returns

Void.

### Parameters

None.

Examples
--------

    var synth = window.speechSynthesis;

    var utterance1 = new SpeechSynthesisUtterance('How about we say this now? This is quite a long sentence to say.');
    var utterance2 = new SpeechSynthesisUtterance('We should say another sentence too, just to be on the safe side.');

    synth.speak(utterance1);
    synth.speak(utterance2);

    synth.pause(); // pauses utterances being spoken

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesis-pause">Web Speech API<br />
<span class="small">The definition of 'pause()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`pause`

33

14

49

No

21

7

No

33

In Android, `pause()` ends the current utterance. `pause()` behaves the same as `cancel()`.

62

In Android, `pause()` ends the current utterance. `pause()` behaves the same as `cancel()`.

No

7

3.0

In Android, `pause()` ends the current utterance. `pause()` behaves the same as `cancel()`.

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/pause" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/pause</a>
