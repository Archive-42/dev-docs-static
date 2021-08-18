# AnalyserNode

The `AnalyserNode` interface represents a node able to provide real-time frequency and time-domain analysis information. It is an [`AudioNode`](audionode) that passes the audio stream unchanged from the input to the output, but allows you to take the generated data, process it, and create audio visualizations.

An `AnalyserNode` has exactly one input and one output. The node works even if the output is not connected.

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI2OTIuOTI5IiBoZWlnaHQ9IjIwNi4zMjMiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzAxMDEwMSIgZD0iTTI1LjU1NiAzMS42Njd2NTkuNDU4Ii8+PHBhdGggZmlsbD0iIzAxMDEwMSIgZD0iTTE5LjcyMiAzMi42NjdsNS44MzQtMTYuODM5IDUuNSAxNi44Mzl6bTIxMC45MTUgNTEuOTE0bDE2LjgzOSA1LjgzNC0xNi44MzkgNS41eiIvPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzAxMDEwMSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBkPSJNMjUuNzIyIDUzLjE2N2gzNi42NjdzNC4xNjctMTQuMzMzIDktMTFjMCAwIDIuMzMzLjQxNyA3LjMzMyAxNCAwIDAgMi45MTcgMTAuNTgzIDggOC4xNjcgMCAwIDMuMzMzLS40MTcgNi42NjctMTQuMTY3IDAgMCAzLjMzMy0xMS45MTcgOC41LTcuMzMzIDAgMCAyLjY2NyAxLjgzMyA2LjUgMTMuMzMzIDAgMCA0IDEyIDguNSA3LjUgMCAwIDMuMzMzLTIuNjY2IDYuMTY3LTEzLjUgMCAwIDMuMTY3LTEyLjY2NyA5LTcuNjY3IDAgMCAyLjI5Mi41NjIgNS42NjcgMTMuNSAwIDAgNC4xNjcgMTMuMDgzIDkuNSA3LjY2NyAwIDAgMi4xODgtMS43MjkgNS0xMy41IDAgMCAzLjI1LTEyLjY2NyA4LjUtNy42NjcgMCAwIDIuOTM4IDMuMjUgNi42NjcgMTMuNjY3IDAgMCA1LjAyMSAxMi4zMzMgOC44MzMgNy42NjcgMCAwIDMuODEyLTQuNjQ2IDQuNjY3LTEwLjU2MWgzMCIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDI1Mi4wNTUgOTQuODM0KSIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxNCI+dDwvdGV4dD48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyMy4yMjIgMTA2LjMzMykiPjx0c3BhbiB4PSIwIiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij4wPC90c3Bhbj48dHNwYW4geD0iNy43ODYiIHk9IjAiIGZvbnQtZmFtaWx5PSInQXJpYWxNVCciIGZvbnQtc2l6ZT0iMTQiIGxldHRlci1zcGFjaW5nPSIyNCI+IDwvdHNwYW4+PHRzcGFuIHg9IjM2IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij4xPC90c3Bhbj48dHNwYW4geD0iNDMuNzg2IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0IiBsZXR0ZXItc3BhY2luZz0iMjQiPiA8L3RzcGFuPjx0c3BhbiB4PSI3MiIgeT0iMCIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxNCI+MjwvdHNwYW4+PHRzcGFuIHg9Ijc5Ljc4NiIgeT0iMCIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxNCIgbGV0dGVyLXNwYWNpbmc9IjI0Ij4gPC90c3Bhbj48dHNwYW4geD0iMTA4IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij4zPC90c3Bhbj48dHNwYW4geD0iMTE1Ljc4NyIgeT0iMCIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxNCIgbGV0dGVyLXNwYWNpbmc9IjI0Ij4gPC90c3Bhbj48dHNwYW4geD0iMTQ0IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij40PC90c3Bhbj48L3RleHQ+PHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDEwMTAxIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik0yNS41NTYgOTAuNjY3aDIwNS4wODEiLz48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiMwMTAxMDEiIGQ9Ik00MzEuNTU2IDMxLjY2N3Y1OS40NTgiLz48cGF0aCBmaWxsPSIjMDEwMTAxIiBkPSJNNDI1LjcyMiAzMi42NjdsNS44MzQtMTYuODM5IDUuNSAxNi44Mzl6bTIxMC45MTQgNTEuOTE0bDE2Ljg0IDUuODM0LTE2Ljg0IDUuNXoiLz48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiMwMTAxMDEiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgZD0iTTQzMS43MjIgNTMuMTY3aDM2LjY2NnM0LjE2Ny0xNC4zMzMgOS0xMWMwIDAgMi4zMzQuNDE3IDcuMzM0IDE0IDAgMCAyLjkxNiAxMC41ODMgOCA4LjE2NyAwIDAgMy4zMzQtLjQxNyA2LjY2Ni0xNC4xNjcgMCAwIDMuMzM0LTExLjkxNyA4LjUtNy4zMzMgMCAwIDIuNjY3IDEuODMzIDYuNSAxMy4zMzMgMCAwIDQgMTIgOC41IDcuNSAwIDAgMy4zMzQtMi42NjYgNi4xNjgtMTMuNSAwIDAgMy4xNjYtMTIuNjY3IDktNy42NjcgMCAwIDIuMjkxLjU2MiA1LjY2NiAxMy41IDAgMCA0LjE2NyAxMy4wODMgOS41IDcuNjY3IDAgMCAyLjE4OC0xLjcyOSA1LTEzLjUgMCAwIDMuMjUtMTIuNjY3IDguNS03LjY2NyAwIDAgMi45MzggMy4yNSA2LjY2NyAxMy42NjcgMCAwIDUuMDIxIDEyLjMzMyA4LjgzMyA3LjY2NyAwIDAgMy44MTItNC42NDYgNC42NjctMTAuNTYxaDMwIi8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNjU4LjA1NSA5NC44MzQpIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij50PC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDQyOS4yMjIgMTA2LjMzMykiPjx0c3BhbiB4PSIwIiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij4wPC90c3Bhbj48dHNwYW4geD0iNy43ODYiIHk9IjAiIGZvbnQtZmFtaWx5PSInQXJpYWxNVCciIGZvbnQtc2l6ZT0iMTQiIGxldHRlci1zcGFjaW5nPSIyNCI+IDwvdHNwYW4+PHRzcGFuIHg9IjM2IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij4xPC90c3Bhbj48dHNwYW4geD0iNDMuNzg2IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0IiBsZXR0ZXItc3BhY2luZz0iMjQiPiA8L3RzcGFuPjx0c3BhbiB4PSI3MiIgeT0iMCIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxNCI+MjwvdHNwYW4+PHRzcGFuIHg9Ijc5Ljc4NiIgeT0iMCIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxNCIgbGV0dGVyLXNwYWNpbmc9IjI0Ij4gPC90c3Bhbj48dHNwYW4geD0iMTA4IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij4zPC90c3Bhbj48dHNwYW4geD0iMTE1Ljc4NyIgeT0iMCIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxNCIgbGV0dGVyLXNwYWNpbmc9IjI0Ij4gPC90c3Bhbj48dHNwYW4geD0iMTQ0IiB5PSIwIiBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjE0Ij40PC90c3Bhbj48L3RleHQ+PHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMDEwMTAxIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik00MzEuNTU2IDkwLjY2N2gyMDUuMDgiLz48cGF0aCBmaWxsPSIjMDEwMTAxIiBkPSJNNDAxLjYzNiA0Ny40ODlsMTYuODQgNS44MzQtMTYuODQgNS41eiIvPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzAxMDEwMSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBkPSJNMjczLjU1NSA1My41NzZoMTI4LjA4MSIvPjxwYXRoIGZpbGw9IiMwMTAxMDEiIGQ9Ik0zNDcuODg5IDE0OC40NTRsLTUuODM0IDE2Ljg0LTUuNS0xNi44NHoiLz48cGF0aCBmaWxsPSIjNzE5RkQwIiBzdHJva2U9IiMwMTAxMDEiIGQ9Ik0yOTkuMjIyIDM1aDg2djk2LjVoLTg2eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDMwNC4yMjMgNTYuODIzKSIgZm9udC1mYW1pbHk9IidBcmlhbE1UJyIgZm9udC1zaXplPSIxMSI+QW5hbHlzZXJOb2RlPC90ZXh0PjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzAxMDEwMSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBkPSJNMzQxLjgwMyAxMTh2MzAuNDU0Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMzMxLjg4OSAxMDYuMzMzKSIgZm9udC1mYW1pbHk9IidBcmlhbC1Cb2xkTVQnIiBmb250LXNpemU9IjExIj5GRlQ8L3RleHQ+PHBhdGggZmlsbD0ibm9uZSIgc3Ryb2tlPSIjMkMyQzc2IiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIGQ9Ik0zMjEuODg5IDg2LjY2N2g0MWwtOCAyOS4zMzNoLTI1LjMzM3oiLz48ZyBmb250LWZhbWlseT0iJ0FyaWFsTVQnIiBmb250LXNpemU9IjExIj48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg0ODQuODkgMTMxLjUpIj51bmNoYW5nZWQgb3V0cHV0PC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDMwMi4yMjMgMTc2LjE2NykiPmZyZXF1ZW5jeSBkYXRhPC90ZXh0PjwvZz48L3N2Zz4=" alt="Without modifying the audio stream, the node allows to get the frequency and time-domain data associated to it, using a FFT." width="693" height="206" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code> (but may be left unconnected)</td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Inheritance

This interface inherits from the following parent interfaces:

## Constructor

[`AnalyserNode()`](analysernode/analysernode)  
Creates a new instance of an `AnalyserNode` object.

## Properties

_Inherits properties from its parent, [`AudioNode`](audionode)_.

[`AnalyserNode.fftSize`](analysernode/fftsize)  
Is an unsigned long value representing the size of the FFT ([Fast Fourier Transform](https://en.wikipedia.org/wiki/Fast_Fourier_transform)) to be used to determine the frequency domain.

[`AnalyserNode.frequencyBinCount`](analysernode/frequencybincount) <span class="badge inline readonly">Read only </span>  
Is an unsigned long value half that of the FFT size. This generally equates to the number of data values you will have to play with for the visualization.

[`AnalyserNode.minDecibels`](analysernode/mindecibels)  
Is a double value representing the minimum power value in the scaling range for the FFT analysis data, for conversion to unsigned byte values — basically, this specifies the minimum value for the range of results when using `getByteFrequencyData()`.

[`AnalyserNode.maxDecibels`](analysernode/maxdecibels)  
Is a double value representing the maximum power value in the scaling range for the FFT analysis data, for conversion to unsigned byte values — basically, this specifies the maximum value for the range of results when using `getByteFrequencyData()`.

[`AnalyserNode.smoothingTimeConstant`](analysernode/smoothingtimeconstant)  
Is a double value representing the averaging constant with the last analysis frame — basically, it makes the transition between values over time smoother.

## Methods

_Inherits methods from its parent, [`AudioNode`](audionode)_.

[`AnalyserNode.getFloatFrequencyData()`](analysernode/getfloatfrequencydata)  
Copies the current frequency data into a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) array passed into it.

[`AnalyserNode.getByteFrequencyData()`](analysernode/getbytefrequencydata)  
Copies the current frequency data into a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) (unsigned byte array) passed into it.

[`AnalyserNode.getFloatTimeDomainData()`](analysernode/getfloattimedomaindata)  
Copies the current waveform, or time-domain, data into a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) array passed into it.

[`AnalyserNode.getByteTimeDomainData()`](analysernode/getbytetimedomaindata)  
Copies the current waveform, or time-domain, data into a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) (unsigned byte array) passed into it.

## Examples

**Note**: See the guide [Visualizations with Web Audio API](web_audio_api/visualizations_with_web_audio_api) for more information on creating audio visualizations.

### Basic usage

The following example shows basic usage of an [`AudioContext`](audiocontext) to create an `AnalyserNode`, then [`requestAnimationFrame`](window/requestanimationframe) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect time domain data repeatedly and draw an "oscilloscope style" output of the current audio input. For more complete applied examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo (see [app.js lines 128–205](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L128-L205) for relevant code).

    var audioCtx = new(window.AudioContext || window.webkitAudioContext)();

    // ...

    var analyser = audioCtx.createAnalyser();
    analyser.fftSize = 2048;

    var bufferLength = analyser.frequencyBinCount;
    var dataArray = new Uint8Array(bufferLength);
    analyser.getByteTimeDomainData(dataArray);

    // Connect the source to be analysed
    source.connect(analyser);

    // Get a canvas defined with ID "oscilloscope"
    var canvas = document.getElementById("oscilloscope");
    var canvasCtx = canvas.getContext("2d");

    // draw an oscilloscope of the current audio source

    function draw() {

      requestAnimationFrame(draw);

      analyser.getByteTimeDomainData(dataArray);

      canvasCtx.fillStyle = "rgb(200, 200, 200)";
      canvasCtx.fillRect(0, 0, canvas.width, canvas.height);

      canvasCtx.lineWidth = 2;
      canvasCtx.strokeStyle = "rgb(0, 0, 0)";

      canvasCtx.beginPath();

      var sliceWidth = canvas.width * 1.0 / bufferLength;
      var x = 0;

      for (var i = 0; i < bufferLength; i++) {

        var v = dataArray[i] / 128.0;
        var y = v * canvas.height / 2;

        if (i === 0) {
          canvasCtx.moveTo(x, y);
        } else {
          canvasCtx.lineTo(x, y);
        }

        x += sliceWidth;
      }

      canvasCtx.lineTo(canvas.width, canvas.height / 2);
      canvasCtx.stroke();
    }

    draw();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#analysernode">Web Audio API<br />
<span class="small">The definition of 'AnalyserNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AnalyserNode`

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

`AnalyserNode`

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

`fftSize`

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

`frequencyBinCount`

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

`getByteFrequencyData`

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

`getByteTimeDomainData`

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

`getFloatFrequencyData`

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

`getFloatTimeDomainData`

14

12

25

No

15

14.1

≤37

18

25

14

14.5

1.0

`maxDecibels`

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

`minDecibels`

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

`smoothingTimeConstant`

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

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode</a>
