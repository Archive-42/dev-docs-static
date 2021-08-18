# ChannelMergerNode

The `ChannelMergerNode` interface, often used in conjunction with its opposite, [`ChannelSplitterNode`](channelsplitternode), reunites different mono inputs into a single output. Each input is used to fill a channel of the output. This is useful for accessing each channels separately, e.g. for performing channel mixing where gain must be separately controlled on each channel.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAR4AAADYCAMAAAAK0Xz5AAAAMFBMVEUGCAcOESMMIkszLCMkM0Q5UGpYWlYzZq1PaoeHhoFijb5wkKZyntGqyOTQyLz9//y/Oyn2AAAFW0lEQVR4AeyW0W4cIQxFjcEMsS31//+2cKHsEk3UafpEBMrG9pnrrHKENqFf3zjXDzjPftPv6fHtz9Fz9Bw9R8/Rc/QcPUfP0fMT9Bw9R8/RY/IoJur/fUrZSY8loqSZ/cmJl/9JPtiwcLXvvNIsO+khVi3+XE8kbZ1R+Lse4t315IDyL3qu53pIN9cTr6GnJHywSEq1WOlj1pSKO7gMPYmxkMKgPa1eN0QWZByvoQc/FlWy9LqDHiPteiiUyHVOJYfXGEkEiYwZegpALGFQpEVL7UNZkLEF6AEN3ivJWNxBT/ChR2df2xz6OJSAGSn0XA1YsDBpJkWs9gsyBmX3EehV5uI+evjVx2uMaD3DRuf4ytzyFiZtANGoCzJu1bgHs6w1XhvqMRG60yPg0NMfWJh06iFdUBNTEQx5Q73KXNzns2f4KCTlKz2i8wJZEzEpXGTWzCsybvgrPaLb/OVafMQbPTzT7al8NBGTZtRISReEwUK50cPb/N/Dqx51pxs9pG96Phg3YLl6FX6+jd1CTFAJ1KsgtYceo+vT7fm40eNR3vQYkfbH8nKRg6quyKCNGHt4I7wEqT30eKaUePrIQcKdHqspGnpqCf3xoJl7gqisiKGU8ZFG3aHEJGNxCz1upair1q696mA+R/PRu0nBjHGmQTHicuTwjhBBCzreTPW1+Ludu1tSFAYCKBwMadOy6X7/t11A3XGYhBJLd/w554K9DPuVMiRdM59z3jPspkvHcdgKT97B0yjssjTf9OA5LF/04OEoHh544IEHHnjggQceeOCBBx544IEHHnjg2f8InrXbhmcTDzw21VoLHpHQS4Gnedux8OWCB54359HwVP3kCRv6qE/Pbuta8MADzxWvhWNVHnjsHDx33JLCA88yeG4PHnjggQceeOCBh9fCZmwq4OFAo74WPDafhsW+wFO/7TjJ6A6eNs90hafNY50/AY/p9nbpYR15BjPpypGnv74H8GhcSep1/ZZu4BGJofiRJ13fB325tF9bi2ePpFt4+MnFa2FK7m4hw9PYVPj878vzsCWFh+MwDlPhgQceeOCBBx54eC1kUwEPPPCYiGhx17ECz6LcDW7xj7tpModnUX9wd50ulh2eZSn5KcvvOiXtb2+vUbRc8nS/+suSKht7+BDZLA5nHtswJc35A75cPmbpzCOFZ8/3/+EaDzzdYBqKu0qvqhGexW2rqo/ZMX8FHjYV8KhamwceCSGqcRzW5gmzEIepTZ6TUJMHnpNQkweek1CTB56paO/Fc9eiGp+er2Rhw7OnwXOyqfDAE9V4LWzwRDU2FQ2ek81787BjZ0pqOgVPY0pq2ptpKPDUp6SWfbrAU5+SzjyaX31K2t9UNxd+9m9Kar2q9O778PxT0jrPA8rnKenM05WRJ1/fB01JLbtb11iLKenas4cpqUmv7h4zPK0p6XyFh00FPBuCh18a+M3ggQceeOCBBx54eC1kUwGPqrbWgseCqHQx19aCx7oyXes88MjgU3qorQVPXFsLnu6JeEw3JVMbJqFhYwue556SPuwPEudW85erXPLkiw4rfc6jOfucVdfiB3scfEwSPNXbtphUY3J4GrdtqsXhYUsKDzwch3GYCg888MADDzzwwMNrIZsKeOCBBx54GqWYi3vMqkWTaoHnW3st7q7FvFgxG3kO9XKl/zwllUbd5SA03LUjj2Vxt9T//pTU5Kt7/UHifH2HRROPuhZzt2I+bPqk5vf/cslg2WUo7pbN8va13pvHxtzM3W3M4Vm/bXjggQceeJ76OAyehwYPPPDAAw888MADDzzwwAMPPPDA0wie8vI9lOcN8qv6Czy9vnK9w4TWAAAAAElFTkSuQmCC" width="286" height="216" />

If `ChannelMergerNode` has one single output, but as many inputs as there are channels to merge; the number of inputs is defined as a parameter of its constructor and the call to [`AudioContext.createChannelMerger()`](baseaudiocontext/createchannelmerger). In the case that no value is given, it will default to `6`.

Using a `ChannelMergerNode`, it is possible to create outputs with more channels than the rendering hardware is able to process. In that case, when the signal is sent to the [`AudioContext.listener`](baseaudiocontext/listener) object, supernumerary channels will be ignored.

<table><tbody><tr class="odd"><td>Number of inputs</td><td>variable; default to <code>6</code>.</td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2 </code>(not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Constructor

[`ChannelMergerNode()`](channelmergernode/channelmergernode)  
Creates a new `ChannelMergerNode` object instance.

## Properties

_No specific property; inherits properties from its parent, [`AudioNode`](audionode)_.

## Methods

_No specific method; inherits methods from its parent, [`AudioNode`](audionode)_.

## Example

The following example shows how you could separate a stereo track (say, a piece of music), and process the left and right channel differently. To use them, you need to use the second and third parameters of the [`AudioNode.connect(AudioNode`](audionode/connect) method, which allow you to specify both the index of the channel to connect from and the index of the channel to connect to.

    var ac = new AudioContext();
    ac.decodeAudioData(someStereoBuffer, function(data) {
     var source = ac.createBufferSource();
     source.buffer = data;
     var splitter = ac.createChannelSplitter(2);
     source.connect(splitter);
     var merger = ac.createChannelMerger(2);

     // Reduce the volume of the left channel only
     var gainNode = ac.createGain();
     gainNode.gain.setValueAtTime(0.5, ac.currentTime);
     splitter.connect(gainNode, 0);

     // Connect the splitter back to the second input of the merger: we
     // effectively swap the channels, here, reversing the stereo image.
     gainNode.connect(merger, 0, 1);
     splitter.connect(merger, 1, 0);

     var dest = ac.createMediaStreamDestination();

     // Because we have used a ChannelMergerNode, we now have a stereo
     // MediaStream we can use to pipe the Web Audio graph to WebRTC,
     // MediaRecorder, etc.
     merger.connect(dest);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#channelmergernode">Web Audio API<br />
<span class="small">The definition of 'ChannelMergerNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ChannelMergerNode`

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

`ChannelMergerNode`

55

79

53

No

42

14.1

55

55

53

42

14.5

6.0

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChannelMergerNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChannelMergerNode</a>
