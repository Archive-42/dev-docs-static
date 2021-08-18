# BiquadFilterNode.getFrequencyResponse()

The `getFrequencyResponse()` method of the [`BiquadFilterNode`](../biquadfilternode) interface takes the current filtering algorithm's settings and calculates the frequency response for frequencies specified in a specified array of frequencies.

The two output arrays, `magResponseOutput` and `phaseResponseOutput`, must be created before calling this method; they must be the same size as the array of input frequency values (`frequencyArray`).

## Syntax

    BiquadFilterNode.getFrequencyResponse(frequencyArray, magResponseOutput, phaseResponseOutput);

### Parameters

`frequencyArray`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing an array of frequencies, specified in Hertz, which you want to filter.

`magResponseOutput`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) to receive the computed magnitudes of the frequency response for each frequency value in the `frequencyArray`. For any frequency in `frequencyArray` whose value is outside the range 0.0 to `sampleRate`/2 (where [`sampleRate`](../baseaudiocontext/samplerate) is the sample rate of the [`AudioContext`](../audiocontext)), the corresponding value in this array is [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN). These are unitless values.

`phaseResponseOutput`  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) to receive the computed phase response values in radians for each frequency value in the input `frequencyArray`. For any frequency in `frequencyArray` whose value is outside the range 0.0 to `sampleRate`/2 (where [`sampleRate`](../baseaudiocontext/samplerate) is the sample rate of the [`AudioContext`](../audiocontext)), the corresponding value in this array is [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN).

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

`InvalidAccessError`  
The three arrays provided are not all of the same length.

## Example

In the following example we are using a biquad filter on a media stream (for the full demo, see our [stream-source-buffer demo](https://mdn.github.io/stream-source-buffer/) live, or [read the source](https://github.com/mdn/stream-source-buffer/blob/gh-pages/index.html).) As part of this demo, we get the frequency responses for this biquad filter, for five sample frequencies. We first create the [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array)s we need, one containing the input frequencies, and two to receive the output magnitude and phase values:

    var myFrequencyArray = new Float32Array(5);
    myFrequencyArray[0] = 1000;
    myFrequencyArray[1] = 2000;
    myFrequencyArray[2] = 3000;
    myFrequencyArray[3] = 4000;
    myFrequencyArray[4] = 5000;

    var magResponseOutput = new Float32Array(5);
    var phaseResponseOutput = new Float32Array(5);

Next we create a [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element in our HTML to contain our results, and grab a reference to it in our JavaScript:

    <p>Biquad filter frequency response for: </p>
    <ul class="freq-response-output">
    </ul>

    var freqResponseOutput = document.querySelector('.freq-response-output');

Finally, after creating our biquad filter, we use `getFrequencyResponse()` to generate the response data and put it in our arrays, then loop through each data set and output them in a human-readable list at the bottom of the page:

    var biquadFilter = audioCtx.createBiquadFilter();
    biquadFilter.type = "lowshelf";
    biquadFilter.frequency.value = 1000;
    biquadFilter.gain.value = range.value;

      ...

    function calcFrequencyResponse() {
      biquadFilter.getFrequencyResponse(myFrequencyArray,magResponseOutput,phaseResponseOutput);

      for(i = 0; i <= myFrequencyArray.length-1;i++){
        var listItem = document.createElement('li');
        listItem.innerHTML = '<strong>' + myFrequencyArray[i] + 'Hz</strong>: Magnitude ' + magResponseOutput[i] + ', Phase ' + phaseResponseOutput[i] + ' radians.';
        freqResponseOutput.appendChild(listItem);
      }
    }

    calcFrequencyResponse();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-biquadfilternode-getfrequencyresponse">Web Audio API<br />
<span class="small">The definition of 'getFrequencyResponse()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`getFrequencyResponse`

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

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/getFrequencyResponse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/getFrequencyResponse</a>
