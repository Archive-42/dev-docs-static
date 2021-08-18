# AudioBufferSourceNode

The `AudioBufferSourceNode` interface is an [`AudioScheduledSourceNode`](audioscheduledsourcenode) which represents an audio source consisting of in-memory audio data, stored in an [`AudioBuffer`](audiobuffer). It's especially useful for playing back audio which has particularly stringent timing accuracy requirements, such as for sounds that must match a specific rhythm and can be kept in memory rather than being played from disk or the network. To play sounds which require accurate timing but must be streamed from the network or played from disk, use a [`AudioWorkletNode`](audioworkletnode) to implement its playback.

An `AudioBufferSourceNode` has no inputs and exactly one output, which has the same number of channels as the `AudioBuffer` indicated by its [`buffer`](audiobuffersourcenode/buffer) property. If there's no buffer set—that is, if `buffer` is `null`—the output contains a single channel of silence (every sample is 0).

An `AudioBufferSourceNode` can only be played once; after each call to [`start()`](audioscheduledsourcenode/start), you have to create a new node if you want to play the same sound again. Fortunately, these nodes are very inexpensive to create, and the actual `AudioBuffer`s can be reused for multiple plays of the sound. Indeed, you can use these nodes in a "fire and forget" manner: create the node, call `start()` to begin playing the sound, and don't even bother to hold a reference to it. It will automatically be garbage-collected at an appropriate time, which won't be until sometime after the sound has finished playing.

Multiple calls to [`stop()`](audioscheduledsourcenode/stop) are allowed. The most recent call replaces the previous one, if the `AudioBufferSourceNode` has not already reached the end of the buffer.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAW0AAADBCAMAAAAzdhExAAAAYFBMVEUCAwAlBzJSAAIXC3AAGl8RHTE+IwAtLit+LzeLNQcaSJhKS0BfUSRDY4EyZ7BocWFTjslljrLHhTxwmZyiknFyntGampxystyoz+vIzsfly5XzznjN9Njb9v3//cz+//yJzXI3AAANOElEQVR42u2ci5aqOgyGA4IcxHIVtuCA7/+WJ0kBAVHwgqNjutao0FL1a/ibNHXgyMV/TjlKuVqgpl09owhtoS20hbbQFtpCW2gLbaEtRWgLbaEttIW20BbaQltoC+1LtOOkqn7GwcYQHUzjR2g/QDu2+khVdVg1By4AJM3BAUHHqhDbfoS227dWop01B//9MOOaNg6Lm4iSPEL7YALiJIvN8W+XI20qxS7XtAmwro2tn8pMuBG3yIX27bRVHLF2HNCoTWcNEb8CjySEaJs/uvYA4GxJWEyH2gAooX0z7ThChSCRQMYo4QeTaaNBH9CUkTZadF1L0PF8vCF1OcCPKMnttN2c2NW0E63bisXa/OFZMqoGtNnm25lUaN9AG126NTS03Za2qQWbZkkz6dN2bceB5KCE9h20rV3hJldoV+6QdlIURSW076FNLshhQ8rRo10rCdGOk7q2oySV0L6LNgE+GBUHLozebWdJQ9M2Ex3WtLR9oX0nbZYMtGJXbYH8voCf+BW51q4XmBTT6NoVocdL1M4S2nfZ9o4DlZ9ql1G0UvATvwoyjnF0JKNrc26JR0HexDZCW9YAhbbQFtpCW2gLbaEttKUIbaEttIW20BbaQltoC22hLbRfTlt+5/5C2k9uKkVofxRtKa+knQktURKhLUUQfhRtT2iJkvxR2o7QEt0WJZEitCWWFNpSREmEthRRkj9BOxdaoiRCW4og/CjagdASJfmjtGXFVXRbbFuK6Lb4JF8Wpr6HwXpC+3UDk4HQfh1tB74kLwT+IuXGDwHet9BOFyj+jUICILQHBZai7SDtTGi/iDbC/hIpeQMlISH5Eim5gbZaiLbDtDOh/RIlYdjfISW/T1sLyXdIye/rtlPTzoR2t9jL0K5hf4WU/LqSNELyFVIyi3YUNbYdqWfTdlramdCuzdph3pGCp9NuYX+DlMyjrYgGW+HTlSSnAvwotGspaezPWSJy/54k3MxZsqEdCe0X0FY17VRov4B2LSVKaL/E37ZvERKh/SBtdcMcKbQfpR3dIiRC+9HI3blBSJainTtO9h20UUrs9HdpZ+A4cHk3YuZ4lwOk3HOuxKrZi4Zx/qrUDUKyDO2MY/uLq1cOBbuXmOUcCl/qOaBhDN6Ktr1YFngm7Xoh5cJ6igM5YQsuweaByi/AzqiJ8za0m9Bd/R5tDxoTz0cNP9fg8vGlL/3kjA9F1nl6A9o23LZQsgTtFoYzxqwxagdGh2LQqn9XOI2JvwftE+yZU+UCtD042WI+IgZng3KuQeNAT90tv+Y7h7aCbnHuoJ1PTPkzaHfMcsS4T7UeXDbtUeM+9bb8Vts5tKFf7qFNo5TlD9Dukjg37m7tuXF3RmfEuDudLW7cd9BW99Em4EF+L+2ePZ9R6daeW353cM7GonsvLK7cM2irAW37btoXgU9/yx6lMyrd2hwuavrYWPRGbmm35A7a8AjtceBwi5AMrPWsdmj5vePhWPRVyXH+HO1hwhfmlD7BgePcPxzMkwOVH0SUfY8xGxj39c+UL0E7gueWe2z7itiexzt9x2PggQ/GYuCk9Mfi6Tr+0lnyAd2+MvEdPefaWAy1uMd36PRd16SX0Hae4gFSud8nuTq3BVe0+MyJ9q5PmsHl6eFFsWRXBmYtlYzS9h7xt6/MmudBSXcsznj2xuKM57IO4bydaTfCHqHtZU/IJswNLR8IdvJFg50b95M8f2fanbQ7NjjiJJ84jQby+RWeiwbys7PA9pvtcGiNe4Rnd5FqZNWvdRizq4tUCzjf7/B7ybtoN0DHl6UboGNDcQI6KhXO1XX0L6XdAL0nQ1CPgQPX/J0llqg+l/ZU9ivgyfnC+wEzzy74O87xSv7zO2kTEOdy+Hw9QQ+TKeNFVkw+mfbx6q6F65tPgontEMtk4D+a9scVoS20hbbQFtpCW2gL7XekPdiiHfhpFJ5+EtypjTzYJGCEQvsB2ttV/3CTBs2ZaA1wap4YEdZGYtsP0I5Ma0g7aVpEdpgGRmv1OAieL0ryCO0EIGTt4D8VIu2If+AeatrR2q9rAytMTL+p6uiN0J5NO7A8tGY02wCfwAbY0KsAHGxHtBMj1LUBgO2gsCSmTW2oodC+lfZ2gwpR00YJT5g2GjQOQxo5YeRZTS224/MrUpcAQlGSm2kjv8Roaft6ltzgKTJqniU3A9rYKDLCYCW6fTttdOkcCBOLeEZmS5u0fB2ykjS1Ne1obaOg+MFGaN9OO7BUtPWv0E6b2pa2T1640L6HNsJF4qQcyG/dVRKUi4a2MVCSNBXa99AmfGnCtBEzeX/rZpZEi45srDTDuraZJS2hfSdtkgx6WFseTYegvMYDVEDoUaIRuq4l2qg16CainyK077Ft3p2jwkhxDJMoFelYRylqphRFMqmuPYVAKhzENl9OO7v4gxdZA1yA9vjG6SIrhfYytEeAu4bQXo72AHgBYO+F9oK0u8BdPPj3JrT/ctE7jCrT2L+Jkhz/rm03v4CuTKsU2ovqdufH5kJ7WZ+k/7v+EdrR1P/pis4yxbx6IrSH/vbZv1CoTFv1fZItDHIwZ2VrDVdFhPZ5LDn23yoqE8Dv0g6MMJ0w7i21fz7tPN/PalU+ocnMRjNbzS9VlpU92nW+XenErk7uUpZXZ3rpwXP06jYtj+iVFaat1EO0Y/JF57SaaFSYMzoqYNa7oS0+/w7t0db5rq3hoJET0q2fABhhALbFmeAw9RSETYaYuONJG9vZsHqAdgG2B6vy8SGJwV6DNdHPAdQWrHLG2IaL0k5YtBNEzUkETVsvcuvMAeUqdRVniENe4DZCzln699OOwecZewLSDJPMsJk1KRHUqJw27YVpk8VyFp0z6Zo272rgMeCznLppM8R1epiu2G4eoR3ijD2l3Lu9O0MAZoCkN9zMEbeFaZM0hIQ5aWkbvIeEB8JxiHa69tucJY0F6nZAW0seou0fXZieJ+fQdqcZIUh72rSt3fK0aUPJibbXpR1GUUi0g9WJNmjaVjRw1H+NdjHDtAvadTT5kdL4BbSDzUlJeHdJR0loMPw0Mr0RJUnfgjY6JemsaXlqTFxQazDS5W37tIMhMZk2z4D1NEiUA1SNrcX7G0y9V+1sX/ECs+Qs2u48r2363VwOvv0laW9ttUb3Ymt5QPt0cHR9zgsHgP40PtQ2negM8ZruAVvRNs2tocB/xAO0gmkPcAZtVGQVqImOYpVNe4B5nqMNlEvSjnSaN9LJ3oSSvXVemKKXpE33Kp0hrgOhSF/4SHTjzoo3ZtGengHjedEN69vSSvI7a4C7bFbknk1bZD7Z6Jhl2azIfdZn+kTa31KEttAW2kJbaAttoS20hfb30V6kCNhx2oJAaAvtXymnFY3KhX0xneK6utA0Iz9QbShz2VkuGaypxP/+Km1aG2xX9ONNXpn7/P7hwi5mzCfVqqygc5H7r9/Z36X9X3ksjPJkVJVx84pzD85M2sfuGmF3X9HBv0672pTXT7w7bbKtku9nNyqLFT7rldCypsCrpxn9m8X8SBWltkBuk+dZ7obNUZXta9q6h2bdlY9IL3JmW9WJhixr7Vn3zKNVIm29ptuu7PILfT1/vrLTIZ/4INooHtqiYrCTLdgo3R7saXcJkatM29njg7k5VoAV6WFFkoNnIKQtIdYOePcEH9lrndelHujkmneexNYW7xgTbxzUj9jYwope6T71zaF7Ptbbp/BzUE1sr3W2CS8x9vX1MRj7A21F6p74HNr7425V1vcvKQmydFPEibT3GhUp6YrGpMLvF/ukNe4/bFBYSCzkW0MfcSu/lYRDJzOHbVyWKWzGvRm69b6mzT23SoIDi33z+9DQ0SV+fT19vsPwxEfNkuGxS5u/JpKqYbGTQUqqOR9WPy7C2ccp3RcV2RXR5iPdqqG9Kjq044Y23RkHTbttjbS555Z22rTk+vqSBm55fuKjZslGSRraqB1bbe+Nw0APcVgzicMCkduOA0yJ7ZaP3BPtnQMW3hb6Hq+2lKWsaWN9wSOq+xylrVuC47GW0amqR3t44rNmyXRAe5/n+fGMdm3bx8PmsMEJFduULW06Op5ox6s9CsVxx6ngylSl26VdnWj7V2hvcr3j+Jz25pNpxyF9IberJPWXPPJtPaBdGdtUnz42tPXRiR++Ynj8QIrinivJJO1Vq0ld4bDK8xOf5ZP8o+9vNrRpluzQ3tQPbsOEIk59+kR70zR1G9pxj7buHD37YlU2ur1p4ppx2q3nT5dgY319Pan0T3zOLKkC0yoLQNevpU1HfkMbdSBAb0RtdQDI33RFQ6R2lg4JY/ufPipo27a2VnsHq4MVmNqHVNy5saONKO5m13iA1GfjAeqeees3zZ/sK1qZyaPhope5r6/Hq9ADHJz4GNp5xmFFke0xliGZzPiIwon6S9DPK/BMpOuqfR37VXwhta6Cf/URtqojop3CF7sg0j0EEfW8w/coqSVKPF2o+9TrJHXPdGVU8sfgC+rwZsdA9fUF0g6LoHdC1gAXLAdfVlyFttCW8sQV+fPyP6IGw7koLvSaAAAAAElFTkSuQmCC" alt="The AudioBufferSourceNode takes the content of an AudioBuffer and m" width="365" height="193" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>0</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count</td><td>defined by the associated <a href="audiobuffer"><code>AudioBuffer</code></a></td></tr></tbody></table>

## Constructor

[`AudioBufferSourceNode()`](audiobuffersourcenode/audiobuffersourcenode)  
Creates and returns a new `AudioBufferSourceNode` object. An [`AudioBufferSourceNode`](audiobuffersourcenode) can be instantiated using the [`AudioContext.createBufferSource()`](baseaudiocontext/createbuffersource) method.

## Properties

_Inherits properties from its parent, [`AudioScheduledSourceNode`](audioscheduledsourcenode)_.

[`AudioBufferSourceNode.buffer`](audiobuffersourcenode/buffer)  
An [`AudioBuffer`](audiobuffer) that defines the audio asset to be played, or when set to the value `null`, defines a single channel of silence (in which every sample is 0.0).

[`AudioBufferSourceNode.detune`](audiobuffersourcenode/detune)  
Is a [k-rate](audioparam#k-rate) [`AudioParam`](audioparam) representing detuning of playback in [cents](https://en.wikipedia.org/wiki/Cent_%28music%29). This value is compounded with `playbackRate` to determine the speed at which the sound is played. Its default value is `0` (meaning no detuning), and its nominal range is -∞ to ∞.

[`AudioBufferSourceNode.loop`](audiobuffersourcenode/loop)  
A Boolean attribute indicating if the audio asset must be replayed when the end of the [`AudioBuffer`](audiobuffer) is reached. Its default value is `false`.

[`AudioBufferSourceNode.loopStart`](audiobuffersourcenode/loopstart) <span class="badge inline optional">Optional</span>  
A floating-point value indicating the time, in seconds, at which playback of the [`AudioBuffer`](audiobuffer) must begin when `loop` is `true`. Its default value is `0` (meaning that at the beginning of each loop, playback begins at the start of the audio buffer).

[`AudioBufferSourceNode.loopEnd`](audiobuffersourcenode/loopend) <span class="badge inline optional">Optional</span>  
A floating-point number indicating the time, in seconds, at which playback of the [`AudioBuffer`](audiobuffer) stops and loops back to the time indicated by `loopStart`, if `loop` is `true`. The default value is `0`.

[`AudioBufferSourceNode.playbackRate`](audiobuffersourcenode/playbackrate)  
An [a-rate](audioparam#a-rate) [`AudioParam`](audioparam) that defines the speed factor at which the audio asset will be played, where a value of 1.0 is the sound's natural sampling rate. Since no pitch correction is applied on the output, this can be used to change the pitch of the sample. This value is compounded with `detune` to determine the final playback rate.

### Event handlers

_Inherits event handlers from its parent, [`AudioScheduledSourceNode`](audioscheduledsourcenode)_.

## Methods

_Inherits methods from its parent, [`AudioScheduledSourceNode`](audioscheduledsourcenode)_.

## Examples

In this example, we create a two-second buffer, fill it with white noise, and then play it using an `AudioBufferSourceNode`. The comments should clearly explain what is going on.

You can also [run the code live](https://mdn.github.io/webaudio-examples/audio-buffer/), or [view the source](https://github.com/mdn/webaudio-examples/blob/master/audio-buffer/index.html).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // Create an empty three-second stereo buffer at the sample rate of the AudioContext
    var myArrayBuffer = audioCtx.createBuffer(2, audioCtx.sampleRate * 3, audioCtx.sampleRate);

    // Fill the buffer with white noise;
    //just random values between -1.0 and 1.0
    for (var channel = 0; channel < myArrayBuffer.numberOfChannels; channel++) {
      // This gives us the actual ArrayBuffer that contains the data
      var nowBuffering = myArrayBuffer.getChannelData(channel);
      for (var i = 0; i < myArrayBuffer.length; i++) {
        // Math.random() is in [0; 1.0]
        // audio needs to be in [-1.0; 1.0]
        nowBuffering[i] = Math.random() * 2 - 1;
      }
    }

    // Get an AudioBufferSourceNode.
    // This is the AudioNode to use when we want to play an AudioBuffer
    var source = audioCtx.createBufferSource();
    // set the buffer in the AudioBufferSourceNode
    source.buffer = myArrayBuffer;
    // connect the AudioBufferSourceNode to the
    // destination so we can hear the sound
    source.connect(audioCtx.destination);
    // start the source playing
    source.start();

For a `decodeAudioData()` example, see the [`AudioContext.decodeAudioData()`](baseaudiocontext/decodeaudiodata) page.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioBufferSourceNode">Web Audio API<br />
<span class="small">The definition of 'AudioBufferSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioBufferSourceNode`

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

`AudioBufferSourceNode`

55

Before version 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before version 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

`buffer`

14

12

25

Firefox currently handles the value `null` incorrectly. Instead of producing a node that generates a single channel of silence, the node becomes unusable and will be ignored if you attempt to connect it to anything.

No

15

6

≤37

18

25

Firefox currently handles the value `null` incorrectly. Instead of producing a node that generates a single channel of silence, the node becomes unusable and will be ignored if you attempt to connect it to anything.

14

6

1.0

`detune`

44

13

40

No

31

14.1

44

44

40

32

14.5

4.0

`loop`

15

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

`loopEnd`

24

12

25

No

15

6

≤37

25

25

14

6

1.5

`loopStart`

24

12

25

No

15

6

≤37

25

25

14

6

1.5

`playbackRate`

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

`start`

24

12

25

No

15

6.1

≤37

25

25

14

7

1.5

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)
- [Web Audio API](web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode</a>
