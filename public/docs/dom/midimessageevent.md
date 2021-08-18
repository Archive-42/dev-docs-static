# MIDIMessageEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MIDIMessageEvent` interface of the [Web MIDI API](web_midi_api) represents the event passed to the <span class="page-not-created">`onmidimessage`</span> event handler of the [`MIDIInput`](midiinput) interface. A `midimessage` event is fired every time a MIDI message is sent from a device represented by a [`MIDIInput`](midiinput), for example when a MIDI keyboard key is pressed, a knob is tweaked, or a slider is moved.

## Constructor

<span class="page-not-created">`MIDIMessageEvent.MIDIMessageEvent`</span>  
Creates a new `MIDIMessageEvent` object instance.

## Properties

<span class="page-not-created">`MIDIConnectionEvent.data`</span>  
A [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) containing the data bytes of a single MIDI message. See the [MIDI specification](https://www.midi.org/specifications-old/item/table-1-summary-of-midi-message) for more information on its form.

**Note**: Even though the [Web MIDI API](https://www.w3.org/TR/webmidi/#midimessageevent-interface) specifies a `receivedTime` property that returns a [`DOMHighResTimeStamp`](domhighrestimestamp), Chrome (the only implementation at the time of writing) does not support that property since the basic [`Event.timeStamp`](event/timestamp) property already returns a [`DOMHighResTimeStamp`](domhighrestimestamp) in Chrome.

## Examples

    // Printing all messages to console
    navigator.requestMIDIAccess().then(midiAccess => {
      Array.from(midiAccess.inputs).forEach(input => {
        input[1].onmidimessage = (msg) => { console.log(msg); }
      })
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-midi-api/#midimessageevent-interface">Web MIDI API<br />
<span class="small">The definition of 'MIDIMessageEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`MIDIMessageEvent`

43

≤79

No

No

30

No

No

43

No

30

No

4.0

`MIDIMessageEvent`

43

≤79

No

No

30

No

No

43

No

30

No

4.0

`data`

43

≤79

No

No

30

No

No

43

No

30

No

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MIDIMessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MIDIMessageEvent</a>
