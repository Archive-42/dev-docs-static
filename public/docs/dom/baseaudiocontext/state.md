# BaseAudioContext.state

The `state` read-only property of the [`BaseAudioContext`](../baseaudiocontext) interface returns the current state of the `AudioContext`.

## Syntax

    baseAudioContext.state;

### Value

A [`DOMString`](../domstring). Possible values are:

- `suspended`: The audio context has been suspended (with the [`AudioContext.suspend()`](../audiocontext/suspend) method.)
- `running`: The audio context is running normally.
- `closed`: The audio context has been closed (with the [`AudioContext.close()`](../audiocontext/close) method.)

## Examples

### Handling state changes

The following snippet is taken from our [AudioContext states demo](https://github.com/mdn/webaudio-examples) ([see it running live](https://mdn.github.io/webaudio-examples/audiocontext-states/).) The [`AudioContext.onstatechange`](onstatechange) handler is used to log the current state to the console every time it changes.

    audioCtx.onstatechange = function() {
      console.log(audioCtx.state);
    }

### Resuming interrupted play states in iOS Safari

In iOS Safari, when a user leaves the page (e.g. switches tabs, minimizes the browser, or turns off the screen) the audio context's state changes to "interrupted" and needs to be resumed. For example:

    function play() {
      if (audioCtx.state === 'interrupted') {
        audioCtx.resume().then(() => play());
        return;
      }
      // ... rest of the play() function
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-state">Web Audio API<br />
<span class="small">The definition of 'state' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`state`

43

14

40

No

Yes

9

Yes

Yes

40

Yes

9

Yes

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/state</a>
