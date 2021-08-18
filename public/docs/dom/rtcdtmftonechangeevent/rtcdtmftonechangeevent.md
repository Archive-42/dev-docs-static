RTCDTMFToneChangeEvent.RTCDTMFToneChangeEvent()
===============================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDTMFToneChangeEvent()` constructor creates a new [`RTCDTMFToneChangeEvent`](../rtcdtmftonechangeevent).

Syntax
------

     var event = new RTCDTMFToneChangeEvent(type, options);

### Parameters

`type`  
A [`DOMString`](../domstring) containing the name of the event. This is always `"tonechange"`.

`options`  
A dictionary of type `RTCDTMFToneChangeEventInit`, which may contain one or more of the following fields:

`tone`  
A [`DOMString`](../domstring) containing a single DTMF tone character which has just begun to play, or an empty string (`""`) to indicate that the previous tone has stopped playing. See [Tone characters](#tone_characters) for details on what characters are permitted.

### Return value

A newly-created [`RTCDTMFToneChangeEvent`](../rtcdtmftonechangeevent), configured as specified in the provided options.

### Tone characters

The digits 0-9  
These characters represent the digit keys on a telephone keypad.

The letters A-D  
These characters represent the "A" through "D" keys which are part of the DTMF standard but not included on most telephones. These are *not* interpreted as digits. Lower-case "a"-"d" automatically gets converted to upper-case.

The pound/hash sign ("\#") and the asterisk ("\*")  
These correspond to the similarly-labeled keys which are typically on the bottom row of the telephone keypad.

The comma (",")  
This character instructs the dialing process to pause for two seconds before sending the next character in the buffer.

All other characters are unrecognized and will cause [`insertDTMF()`](../rtcdtmfsender/insertdtmf) to throw an `InvalidCharacterError` exception.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdtmftonechangeevent">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDTMFToneChangeEvent()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCDTMFToneChangeEvent`

27

≤18

52

No

Yes

13.1

4.4

27

52

Yes

13.4

1.5

See also
--------

-   [WebRTC](../webrtc_api)
-   [Using DTMF with WebRTC](../webrtc_api/using_dtmf)
-   Its usual target: [`RTCDTMFSender`](../rtcdtmfsender).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent/RTCDTMFToneChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent/RTCDTMFToneChangeEvent</a>
