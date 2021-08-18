Using IIR filters
=================

The `IIRFilterNode` interface of the [Web Audio API](../web_audio_api) is an [`AudioNode`](../audionode) processor that implements a general [infinite impulse response](https://en.wikipedia.org/wiki/infinite%20impulse%20response) (IIR) filter; this type of filter can be used to implement tone control devices and graphic equalizers, and the filter response parameters can be specified, so that it can be tuned as needed. This article looks at how to implement one, and use it in a simple example.

Demo
----

Our simple example for this guide provides a play/pause button that starts and pauses audio play, and a toggle that turns an IIR filter on and off, altering the tone of the sound. It also provides a canvas on which is drawn the frequency response of the audio, so you can see what effect the IIR filter has.

<img src="data:image/png;base64,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" alt="A demo featuring a play button, and toggle to turn a filter on and off, and a line graph showing the filter frequencies returned after the filter has been applied." width="620" height="621" />

You can check out the [full demo here on Codepen](https://codepen.io/Rumyra/pen/oPxvYB/). Also see the [source code on GitHub](https://github.com/mdn/webaudio-examples/tree/master/iirfilter-node). It includes some different coefficient values for different lowpass frequencies — you can change the value of the `filterNumber` constant to a value between 0 and 3 to check out the different available effects.

Browser support
---------------

[IIR filters](../iirfilternode) are supported well across modern browsers, although they have been implemented more recently than some of the more longstanding Web Audio API features, like [Biquad filters](../biquadfilternode).

The IIRFilterNode
-----------------

The Web Audio API now comes with an [`IIRFilterNode`](../iirfilternode) interface. But what is this and how does it differ from the [`BiquadFilterNode`](../biquadfilternode) we have already?

An IIR filter is a **infinite impulse response filter**. It's one of two primary types of filters used in audio and digital signal processing. The other type is FIR — **finite impulse response filter**. There's a really good overview to [IIF filters and FIR filters here](https://dspguru.com/dsp/faqs/iir/basics/).

A biquad filter is actually a *specific type* of infinite impulse response filter. It's a commonly-used type and we already have it as a node in the Web Audio API. If you choose this node the hard work is done for you. For instance, if you want to filter lower frequencies from your sound, you can set the [type](../biquadfilternode/type) to `highpass` and then set which frequency to filter from (or cut off). [There's more information on how biquad filters work here](https://www.earlevel.com/main/2003/02/28/biquads/).

When you are using an [`IIRFilterNode`](../iirfilternode) instead of a [`BiquadFilterNode`](../biquadfilternode) you are creating the filter yourself, rather than just choosing a pre-programmed type. So you can create a highpass filter, or a lowpass filter, or a more bespoke one. And this is where the IIR filter node is useful — you can create your own if none of the alaready available settings is right for what you want. As well as this, if your audio graph needed a highpass and a bandpass filter within it, you could just use one IIR filter node in place of the two biquad filter nodes you would otherwise need for this.

With the IIRFIlter node it's up to you to set what `feedforward` and `feedback` values the filter needs — this determines the characteristics of the filter. The downside is that this involves some complex maths.

If you are looking to learn more there's some [information about the maths behind IIR filters here](http://ece.uccs.edu/~mwickert/ece2610/lecture_notes/ece2610_chap8.pdf). This enters the realms of signal processing theory — don't worry if you look at it and feel like it's not for you.

If you want to play with the IIR filter node and need some values to help along the way, there's [a table of already calculated values here](https://www.dspguide.com/CH20.PDF); on pages 4 & 5 of the linked PDF the a*n* values refer to the `feedForward` values and the b*n* values refer to the `feedback`. [musicdsp.org](http://musicdsp.org/) is also a great resource if you want to read more about different filters and how they are implemented digitally.

With that all in mind, let's take a look at the code to create an IIR filter with the Web Audio API.

Setting our IIRFilter co-efficients
-----------------------------------

When creating an IIR filter, we pass in the `feedforward` and `feedback` coefficients as options (coefficients is how we describe the values). Both of these parameters are arrays, neither of which can be larger than 20 items.

When setting our coefficients, the `feedforward` values can't all be set to zero, otherwise nothing would be sent to the filter. Something like this is acceptable:

    let feedForward = [0.00020298, 0.0004059599, 0.00020298];

Our `feedback` values cannot start with zero, otherwise on the first pass nothing would be sent back:

    let feedBackward = [1.0126964558, -1.9991880801, 0.9873035442];

**Note**: These values are calculated based on the lowpass filter specified in the [filter characteristics of the Web Audio API specification](https://webaudio.github.io/web-audio-api/#filters-characteristics). As this filter node gains more popularity we should be able to collate more coefficient values.

Using an IIRFilter in an audio graph
------------------------------------

Let's create our context and our filter node:

    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioCtx = new AudioContext();

    const iirFilter = audioCtx.createIIRFilter(feedForward, feedBack);

We need a sound source to play. We set this up using a custom function, `playSoundNode()`, which [creates a buffer source](../baseaudiocontext/createbuffersource) from an existing [`AudioBuffer`](../audiobuffer), attaches it to the default destination, starts it playing, and returns it:

    function playSourceNode(audioContext, audioBuffer) {
      const soundSource = audioContext.createBufferSource();
      soundSource.buffer = audioBuffer;
      soundSource.connect(audioContext.destination);
      soundSource.start();
      return soundSource;
    }

This function is called when the play button is pressed. The play button HTML looks like this:

    <button class="button-play" role="switch" data-playing="false" aria-pressed="false">Play</button>

And the `click` event listener starts like so:

    playButton.addEventListener('click', function() {
        if (this.dataset.playing === 'false') {
            srcNode = playSourceNode(audioCtx, sample);
            ...
    }, false);

The toggle that turns the IIR filter on and off is set up in the similar way. First, the HTML:

    <button class="button-filter" role="switch" data-filteron="false" aria-pressed="false" aria-describedby="label" disabled></button>

The filter button's `click` handler then connects the `IIRFilter` up to the graph, between the source and the detination:

    filterButton.addEventListener('click', function() {
        if (this.dataset.filteron === 'false') {
            srcNode.disconnect(audioCtx.destination);
            srcNode.connect(iirfilter).connect(audioCtx.destination);
            ...
    }, false);

### Frequency response

We only have one method available on [`IIRFilterNode`](../iirfilternode) instances, `getFrequencyResponse()`, this allows us to see what is happening to the frequencies of the audio being passed into the filter.

Let's draw a frequency plot of the filter we've created with the data we get back from this method.

We need to create three arrays. One of frequency values for which we want to receive the magnitude response and phase response for, and two empty arrays to receive the data. All three of these have to be of type [`float32array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) and all be of the same size.

    // arrays for our frequency response
    const totalArrayItems = 30;
    let myFrequencyArray = new Float32Array(totalArrayItems);
    let magResponseOutput = new Float32Array(totalArrayItems);
    let phaseResponseOutput = new Float32Array(totalArrayItems);

Let's fill our first array with frequency values we want data to be returned on:

    myFrequencyArray = myFrequencyArray.map(function(item, index) {
        return Math.pow(1.4, index);
    });

We could go for a linear approach, but it's far better when working with frequencies to take a log approach, so let's fill our array with frequency values that get larger further on in the array items.

Now let's get our response data:

    iirFilter.getFrequencyResponse(myFrequencyArray, magResponseOutput, phaseResponseOutput);

We can use this data to draw a filter frequency plot. We'll do so on a 2d canvas context.

    // create a canvas element and append it to our dom
    const canvasContainer = document.querySelector('.filter-graph');
    const canvasEl = document.createElement('canvas');
    canvasContainer.appendChild(canvasEl);

    // set 2d context and set dimesions
    const canvasCtx = canvasEl.getContext('2d');
    const width = canvasContainer.offsetWidth;
    const height = canvasContainer.offsetHeight;
    canvasEl.width = width;
    canvasEl.height = height;

    // set background fill
    canvasCtx.fillStyle = 'white';
    canvasCtx.fillRect(0, 0, width, height);

    // set up some spacing based on size
    const spacing = width/16;
    const fontSize = Math.floor(spacing/1.5);

    // draw our axis
    canvasCtx.lineWidth = 2;
    canvasCtx.strokeStyle = 'grey';

    canvasCtx.beginPath();
    canvasCtx.moveTo(spacing, spacing);
    canvasCtx.lineTo(spacing, height-spacing);
    canvasCtx.lineTo(width-spacing, height-spacing);
    canvasCtx.stroke();

    // axis is gain by frequency -> make labels
    canvasCtx.font = fontSize+'px sans-serif';
    canvasCtx.fillStyle = 'grey';
    canvasCtx.fillText('1', spacing-fontSize, spacing+fontSize);
    canvasCtx.fillText('g', spacing-fontSize, (height-spacing+fontSize)/2);
    canvasCtx.fillText('0', spacing-fontSize, height-spacing+fontSize);
    canvasCtx.fillText('Hz', width/2, height-spacing+fontSize);
    canvasCtx.fillText('20k', width-spacing, height-spacing+fontSize);

    // loop over our magnitude response data and plot our filter

    canvasCtx.beginPath();

    for(let i = 0; i < magResponseOutput.length; i++) {

        if (i === 0) {
            canvasCtx.moveTo(spacing, height-(magResponseOutput[i]*100)-spacing );
        } else {
            canvasCtx.lineTo((width/totalArrayItems)*i, height-(magResponseOutput[i]*100)-spacing );
        }

    }

    canvasCtx.stroke();

Summary
-------

That's it for our IIRFilter demo. This should have shown you how to use the basics, and helped you to understand what it's useful for and how it works.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_IIR_filters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_IIR_filters</a>
