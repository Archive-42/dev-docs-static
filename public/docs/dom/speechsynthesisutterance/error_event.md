SpeechSynthesisUtterance: error event
=====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `error` event of the [Web Speech API](../web_speech_api) [`SpeechSynthesisUtterance`](../speechsynthesisutterance) object is fired when an error occurs that prevents the utterance from being successfully spoken.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../speechsynthesiserrorevent"><code>SpeechSynthesisErrorEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onerror</code></td></tr></tbody></table>

Examples
--------

You can use the `error` event in an `addEventListener` method:

    utterThis.addEventListener('error', function(event) {
      console.log('An error has occurred with the speech synthesis: ' + event.error');
    });

Or use the `onerror` event handler property:

    utterThis.onerror = function(event) {
      console.log('An error has occurred with the speech synthesis: ' + event.error');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#utterance-events">Web Speech API<br />
<span class="small">The definition of 'speech synthesis utterance events' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`error_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/error_event</a>
