OfflineAudioCompletionEvent
===========================

The [Web Audio API](web_audio_api) `OfflineAudioCompletionEvent` interface represents events that occur when the processing of an [`OfflineAudioContext`](offlineaudiocontext) is terminated. The `complete` event implements this interface.

**Note**: This interface is marked as deprecated; it is still supported for legacy reasons, but it will soon be superseded when the promise version of [`OfflineAudioContext.startRendering`](offlineaudiocontext/startrendering) is supported in browsers, which will no longer need it.

Constructor
-----------

[`OfflineAudioCompletionEvent.OfflineAudioCompletionEvent`](offlineaudiocompletionevent/offlineaudiocompletionevent)  
Creates a new `OfflineAudioCompletionEvent` object instance.

Properties
----------

*Also inherits properties from its parent, [`Event`](event)*.

 [`OfflineAudioCompletionEvent.renderedBuffer`](offlineaudiocompletionevent/renderedbuffer) <span class="badge inline readonly">Read only </span>   
An [`AudioBuffer`](audiobuffer) containing the result of processing an [`OfflineAudioContext`](offlineaudiocontext).

Methods
-------

*Inherits methods from its parent, [`Event`](event)*.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#OfflineAudioCompletionEvent">Web Audio API<br />
<span class="small">The definition of 'OfflineAudioCompletionEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`OfflineAudioCompletionEvent`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

`OfflineAudioCompletionEvent`

57

Before Chrome 59, the default values were not supported.

≤79

53

No

42

Yes

57

Before version 59, the default values were not supported.

57

Before Chrome 59, the default values were not supported.

53

42

Yes

6.0

Before Samsung Internet 7.0, the default values were not supported.

`renderedBuffer`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

See also
--------

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioCompletionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioCompletionEvent</a>
