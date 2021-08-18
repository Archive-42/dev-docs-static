MIDIConnectionEvent
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MIDIConnectionEvent` interface of the [Web MIDI API](web_midi_api) is the event passed to the <span class="page-not-created">`onstatechange`</span> event handler of the [`MIDIAccess`](midiaccess) interface and the <span class="page-not-created">`onstatechange`</span> event of the <span class="page-not-created">`MIDIPorts`</span> interface. This occurs any time a new port becomes available, or when a previously available port becomes unavailable. For example, this event is fired whenever a MIDI device is either plugged in to or unplugged from a computer.

Constructor
-----------

<span class="page-not-created">`MIDIConnectionEvent.MIDIConnectionEvent`</span>  
Creates a new `MIDIConnectionEvent` object.

Properties
----------

<span class="page-not-created">`MIDIConnectionEvent.port`</span>  
Returns a reference to a <span class="page-not-created">`MIDIPort`</span> instance for a port that has been connected or disconnected."

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-midi-api/#midiconnectionevent-interface">Web MIDI API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MIDIConnectionEvent`

43

≤79

No

No

30

No

43

43

No

30

No

4.0

`MIDIConnectionEvent`

43

≤79

No

No

30

No

43

43

No

30

No

4.0

`port`

43

≤79

No

No

30

No

43

43

No

30

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MIDIConnectionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MIDIConnectionEvent</a>
