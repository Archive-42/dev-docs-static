# MIDIAccess

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MIDIAccess` interface of the [Web MIDI API](web_midi_api) provides methods for listing MIDI input and output devices, and obtaining access to those devices.

## Properties

<span class="page-not-created">`MIDIAccess.inputs`</span> <span class="badge inline readonly">Read only </span>  
Returns an instance of [`MIDIInputMap`](midiinputmap) which provides access to any available MIDI input ports.

<span class="page-not-created">`MIDIAccess.outputs`</span> <span class="badge inline readonly">Read only </span>  
Returns an instance of [`MIDIOutputMap`](midioutputmap) which provides access to any available MIDI output ports.

<span class="page-not-created">`MIDIAccess.sysexEnabled`</span> <span class="badge inline readonly">Read only </span>  
A boolean attribute indicating whether system exclusive support is enabled on the current MIDIAccess instance.

### Event Handlers

<span class="page-not-created">`MIDIAccess.onstatechange`</span>  
Called whenever a new MIDI port is added or an existing port changes state.

## Examples

    navigator.requestMIDIAccess()
      .then(function(access) {

         // Get lists of available MIDI controllers
         const inputs = access.inputs.values();
         const outputs = access.outputs.values();

         access.onstatechange = function(e) {

           // Print information about the (dis)connected MIDI controller
           console.log(e.port.name, e.port.manufacturer, e.port.state);
         };
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-midi-api/#midiaccess-interface">Web MIDI API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MIDIAccess`

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

`inputs`

43

≤79

No

No

Yes

No

43

43

No

Yes

No

4.0

`onstatechange`

43

79

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

`outputs`

43

≤79

No

No

Yes

No

43

43

No

Yes

No

4.0

`statechange_event`

43

≤79

No

No

?

No

43

43

No

?

No

4.0

`sysexEnabled`

45

≤79

No

No

Yes

No

45

45

No

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MIDIAccess" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MIDIAccess</a>
