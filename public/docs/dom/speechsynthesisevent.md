SpeechSynthesisEvent
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechSynthesisEvent` interface of the [Web Speech API](web_speech_api) contains information about the current state of [`SpeechSynthesisUtterance`](speechsynthesisutterance) objects that have been processed in the speech service.

Properties
----------

*The [`SpeechSynthesisEvent`](speechsynthesisevent) interface also inherits properties from its parent interface, [`Event`](event).*

 [`SpeechSynthesisEvent.charIndex`](speechsynthesisevent/charindex) <span class="badge inline readonly">Read only </span>   
Returns the index position of the character in the [`SpeechSynthesisUtterance.text`](speechsynthesisutterance/text) that was being spoken when the event was triggered.

 [`SpeechSynthesisEvent.elapsedTime`](speechsynthesisevent/elapsedtime) <span class="badge inline readonly">Read only </span>   
Returns the elapsed time in milliseconds after the [`SpeechSynthesisUtterance.text`](speechsynthesisutterance/text) started being spoken that the event was triggered at.

 [`SpeechSynthesisEvent.name`](speechsynthesisevent/name) <span class="badge inline readonly">Read only </span>   
Returns the name associated with certain types of events occurring as the [`SpeechSynthesisUtterance.text`](speechsynthesisutterance/text) is being spoken: the name of the [SSML](https://www.w3.org/TR/speech-synthesis/#S3.3.2) marker reached in the case of a `mark` event, or the type of boundary reached in the case of a `boundary` event.

 [`SpeechSynthesisEvent.utterance`](speechsynthesisevent/utterance) <span class="badge inline readonly">Read only </span>   
Returns the [`SpeechSynthesisUtterance`](speechsynthesisutterance) instance that the event was triggered on.

Methods
-------

*The [`SpeechSynthesisEvent`](speechsynthesisevent) interface also inherits methods from its parent interface, [`Event`](event).*

Examples
--------

    utterThis.onpause = function(event) {
      var char = event.utterance.text.charAt(event.charIndex);
      console.log('Speech paused at character ' + event.charIndex + ' of "' +
      event.utterance.text + '", which is "' + char + '".');
    }

    utterThis.onboundary = function(event) {
      console.log(event.name + ' boundary reached after ' + event.elapsedTime + ' milliseconds.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechsynthesisevent">Web Speech API<br />
<span class="small">The definition of 'SpeechSynthesisEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechSynthesisEvent`

33

≤18

49

No

21

7

No

See [bug 487255](https://crbug.com/487255)

33

62

No

7

3.0

`charIndex`

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

-   [Web Speech API](web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisEvent</a>
