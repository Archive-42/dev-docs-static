SpeechSynthesisUtterance: boundary event
========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `boundary` event of the [Web Speech API](../web_speech_api) is fired when the spoken utterance reaches a word or sentence boundary.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../speechsynthesisevent"><code>SpeechSynthesisEvent</code></a></td></tr><tr class="even"><td>Event handler</td><td><code>onboundary</code></td></tr></tbody></table>

Examples
--------

You can use the `boundary` event in an `addEventListener` method:

    utterThis.addEventListener('boundary', function(event) {
      console.log(event.name + ' boundary reached after ' + event.elapsedTime + ' milliseconds.');
    });

Or use the `onboundary` event handler property:

    utterThis.onboundary = function(event) {
      console.log(event.name + ' boundary reached after ' + event.elapsedTime + ' milliseconds.');
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

`boundary_event`

33

14

49

No

21

7

No

33

The `boundary` event does not fire as expected. See [bug 1122143](https://crbug.com/1122143).

62

No

7

3.0

See also
--------

-   [Web Speech API](../web_speech_api)
-   `onboundary`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/boundary_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/boundary_event</a>
