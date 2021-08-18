# BaseAudioContext.createChannelSplitter()

The `createChannelSplitter()` method of the [`BaseAudioContext`](../baseaudiocontext) Interface is used to create a [`ChannelSplitterNode`](../channelsplitternode), which is used to access the individual channels of an audio stream and process them separately.

## Syntax

    baseAudioContext.createChannelSplitter(numberOfOutputs);

### Parameters

numberOfOutputs  
The number of channels in the input audio stream that you want to output separately; the default is 6 if this parameter is not specified.

### Returns

A [`ChannelSplitterNode`](../channelsplitternode).

## Example

The following simple example shows how you could separate a stereo track (say, a piece of music), and process the left and right channel differently. To use them, you need to use the second and third parameters of the [`AudioNode.connect(AudioNode`](../audionode/connect) method, which allow you to specify the index of the channel to connect from and the index of the channel to connect to.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createchannelsplitter">Web Audio API<br />
<span class="small">The definition of 'createChannelSplitter()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createChannelSplitter`

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

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createChannelSplitter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createChannelSplitter</a>
