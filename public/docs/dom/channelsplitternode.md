# ChannelSplitterNode

The `ChannelSplitterNode` interface, often used in conjunction with its opposite, [`ChannelMergerNode`](channelmergernode), separates the different channels of an audio source into a set of mono outputs. This is useful for accessing each channel separately, e.g. for performing channel mixing where gain must be separately controlled on each channel.

<img src="data:image/png;base64,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" width="286" height="216" />

If your `ChannelSplitterNode` always has one single input, the amount of outputs is defined by a parameter on its constructor and the call to [`AudioContext.createChannelSplitter()`](baseaudiocontext/createchannelsplitter). In the case that no value is given, it will default to `6`. If there are fewer channels in the input than there are outputs, supernumerary outputs are silent.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td>variable; default to <code>6</code>.</td></tr><tr class="odd"><td>Channel count mode</td><td><code>"explicit</code>" Older implementations, as per earlier versions of the spec use <code>"max"</code>.</td></tr><tr class="even"><td>Channel count</td><td>Fixed to the number of outputs. Older implementations, as per earlier versions of the spec use <code>2 </code>(not used in the default count mode).</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"discrete"</code></td></tr></tbody></table>

## Constructor

[`ChannelSplitterNode()`](channelsplitternode/channelsplitternode)  
Creates a new `ChannelSplitterNode` object instance.

## Properties

_No specific property; inherits properties from its parent, [`AudioNode`](audionode)_.

## Methods

_No specific method; inherits methods from its parent, [`AudioNode`](audionode)_.

## Example

The following simple example shows how you could separate a stereo track (say, a piece of music), and process the left and right channel differently. To use them, you need to use the second and third parameters of the [`AudioNode.connect(AudioNode`](audionode/connect) method, which allow you to specify the index of the channel to connect from and the index of the channel to connect to.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#channelsplitternode">Web Audio API<br />
<span class="small">The definition of 'ChannelSplitterNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ChannelSplitterNode`

14

Starting in Chrome 56, `channelCountMode` is set to `explicit` and `channelCount` is fixed to the number of outputs, as per the latest spec.

12

25

No

15

Starting in Opera 43, `channelCountMode` is set to `explicit` and `channelCount` is fixed to the number of outputs, as per the latest spec.

6

≤37

Starting in version 56, `channelCountMode` is set to `explicit` and `channelCount` is fixed to the number of outputs, as per the latest spec.

18

Starting in Chrome 56, `channelCountMode` is set to `explicit` and `channelCount` is fixed to the number of outputs, as per the latest spec.

25

14

Starting in Opera 43, `channelCountMode` is set to `explicit` and `channelCount` is fixed to the number of outputs, as per the latest spec.

Yes

1.0

Starting in Samsung Internet 6.0, `channelCountMode` is set to `explicit` and `channelCount` is fixed to the number of outputs, as per the latest spec.

`ChannelSplitterNode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChannelSplitterNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChannelSplitterNode</a>
