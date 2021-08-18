Advanced techniques: Creating and sequencing audio
==================================================

In this tutorial, we're going to cover sound creation and modification, as well as timing and scheduling. We're going to introduce sample loading, envelopes, filters, wavetables, and frequency modulation. If you're familiar with these terms and you're looking for an introduction to their application within with the Web Audio API, you've come to the right place.

Demo
----

We're going to be looking at a very simple step sequencer:

<img src="data:image/png;base64,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" alt="A sound sequencer application featuring play and BPM master controls, and 4 different voices with controls for each." width="841" height="655" />  

In practice this is easier to do with a library — the Web Audio API was built to be built upon. If you are about to embark on building something more complex, [tone.js](https://tonejs.github.io/) would be a good place to start. However, we want to demonstrate how to build such a demo from first principles, as a learning exercise.

**Note**: You can find the source code on GitHub as [step-sequencer](https://github.com/mdn/webaudio-examples/tree/master/step-sequencer); see the [step-sequencer running live](https://mdn.github.io/webaudio-examples/step-sequencer/) also.

The interface consists of master controls, which allow us to play/stop the sequencer, and adjust the BPM (beats per minute) to speed up or slow down the "music".

There are four different sounds, or voices, which can be played. Each voice has four buttons, which represent four beats in one bar of music. When they are enabled the note will sound. When the instrument plays, it will move across this set of beats and loop the bar.

Each voice also has local controls, which allow you to manipulate the effects or parameters particular to each technique we are using to create those voices. The techniques we are using are:

<table><thead><tr class="header"><th>Name of voice</th><th>Technique</th><th>Associated Web Audio API feature</th></tr></thead><tbody><tr class="odd"><td>"Sweep"</td><td>Oscillator, periodic wave</td><td><a href="../oscillatornode"><code>OscillatorNode</code></a>, <a href="../periodicwave"><code>PeriodicWave</code></a></td></tr><tr class="even"><td>"Pulse"</td><td>Multiple oscillators</td><td><a href="../oscillatornode"><code>OscillatorNode</code></a></td></tr><tr class="odd"><td>"Noise"</td><td>Random noise buffer, Biquad filter</td><td><a href="../audiobuffer"><code>AudioBuffer</code></a>, <a href="../audiobuffersourcenode"><code>AudioBufferSourceNode</code></a>, <a href="../biquadfilternode"><code>BiquadFilterNode</code></a></td></tr><tr class="even"><td>"Dial up"</td><td>Loading a sound sample to play</td><td><a href="../baseaudiocontext/decodeaudiodata"><code>BaseAudioContext/decodeAudioData</code></a>, <a href="../audiobuffersourcenode"><code>AudioBufferSourceNode</code></a></td></tr></tbody></table>

**Note**: This instrument was not created to sound good, it was created to provide demonstration code and represents a *very* simplified version of such an instrument. The sounds are based on a dial-up modem. If you are unaware of how one sounds you can [listen to one here](https://soundcloud.com/john-pemberton/modem-dialup).

Creating an audio context
-------------------------

As you should be used to by now, each Web Audio API app starts with an audio context:

    // for cross browser compatibility
    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioCtx = new AudioContext();

The "sweep" — oscillators, periodic waves, and envelopes
--------------------------------------------------------

For what we will call the "sweep" sound, that first noise you hear when you dial up, we're going to create an oscillator to generate the sound.

The [`OscillatorNode`](../oscillatornode) comes with basic waveforms out of the box — sine, square, triangle or sawtooth. However, instead of using the standard waves that come by default, we're going to create our own using the [`PeriodicWave`](../periodicwave) interface and values set in a wavetable. We can use the [`BaseAudioContext.createPeriodicWave`](../baseaudiocontext/createperiodicwave) method to use this custom wave with an oscillator.

### The periodic wave

First of all, we'll create our periodic wave. To do so, We need to pass real and imaginary values into the [`BaseAudioContext.createPeriodicWave()`](../baseaudiocontext/createperiodicwave) method.:

    const wave = audioCtx.createPeriodicWave(wavetable.real, wavetable.imag);

**Note**: In our example the wavetable is held in a separate JavaScript file (`wavetable.js`), because there are *so* many values. It is taken from a [repository of wavetables,](https://github.com/GoogleChromeLabs/web-audio-samples/tree/gh-pages/samples/audio/wave-tables) which can be found in the [Web Audio API examples from Google Chrome Labs](https://github.com/GoogleChromeLabs/web-audio-samples/).

### The Oscillator

Now we can create an [`OscillatorNode`](../oscillatornode) and set its wave to the one we've created:

    function playSweep(time) {
         const osc = audioCtx.createOscillator();
         osc.setPeriodicWave(wave);
         osc.frequency.value = 440;
         osc.connect(audioCtx.destination);
         osc.start(time);
         osc.stop(time + 1);
    }

We pass in a time parameter to the function here, which we'll use later to schedule the sweep.

### Controlling amplitude

This is great, but wouldn't it be nice if we had an amplitude envelope to go with it? Let's create a simple one so we get used to the methods we need to create an envelope with the Web Audio API.

Let's say our envelope has attack and release. We can allow the user to control these using [range inputs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range) on the interface:

    <label for="attack">Attack</label>
    <input name="attack" id="attack" type="range" min="0" max="1" value="0.2" step="0.1" />

    <label for="release">Release</label>
    <input name="release" id="release" type="range" min="0" max="1" value="0.5" step="0.1" />

Now we can create some variables over in JavaScript and have them change when the input values are updated:

    let attackTime = 0.2;
    const attackControl = document.querySelector('#attack');
    attackControl.addEventListener('input', function() {
        attackTime = Number(this.value);
    }, false);

    let releaseTime = 0.5;
    const releaseControl = document.querySelector('#release');
    releaseControl.addEventListener('input', function() {
        releaseTime = Number(this.value);
    }, false);

### The final playSweep() function

Now we can expand our `playSweep()` function. We need to add a [`GainNode`](../gainnode) and connect that through our audio graph to actually apply amplitude variations to our sound. The gain node has one property: `gain`, which is of type [`AudioParam`](../audioparam).

This is really useful — now we can start to harness the power of the audio param methods on the gain value. We can set a value at a certain time, or we can change it *over* time with methods such as [`AudioParam.linearRampToValueAtTime`](../audioparam/linearramptovalueattime).

For our attack and release, we'll use the `linearRampToValueAtTime` method as mentioned above. It takes two parameters — the value you want to set the parameter you are changing to (in this case the gain) and when you want to do this. In our case *when* is controlled by our inputs. So in the example below the gain is being increased to 1, at a linear rate, over the time the attack range input has been set to. Similarly, for our release, the gain is being set to 0, at a linear rate, over the time the release input has been set to.

    let sweepLength = 2;
    function playSweep(time) {
        let osc = audioCtx.createOscillator();
        osc.setPeriodicWave(wave);
        osc.frequency.value = 440;

        let sweepEnv = audioCtx.createGain();
        sweepEnv.gain.cancelScheduledValues(time);
        sweepEnv.gain.setValueAtTime(0, time);
        // set our attack
        sweepEnv.gain.linearRampToValueAtTime(1, time + attackTime);
        // set our release
        sweepEnv.gain.linearRampToValueAtTime(0, time + sweepLength - releaseTime);

        osc.connect(sweepEnv).connect(audioCtx.destination);
        osc.start(time);
        osc.stop(time + sweepLength);
    }

The "pulse" — low frequency oscillator modulation
-------------------------------------------------

Great, now we've got our sweep! Let's move on and take a look at that nice pulse sound. We can achieve this with a basic oscillator, modulated with a second oscillator.

### Initial oscillator

We'll set up our first [`OscillatorNode`](../oscillatornode) the same way as our sweep sound, except we won't use a wavetable to set a bespoke wave — we'll just use the default `sine` wave:

    const osc = audioCtx.createOscillator();
    osc.type = 'sine';
    osc.frequency.value = 880;

Now we're going to create a [`GainNode`](../gainnode), as it's the `gain` value that we will oscillate with our second, low frequency oscillator:

    const amp = audioCtx.createGain();
    amp.gain.setValueAtTime(1, audioCtx.currentTime);

### Creating the second, low frequency, oscillator

We'll now create a second — `square` — wave (or pulse) oscillator, to alter the amplification of our first sine wave:

    const lfo = audioCtx.createOscillator();
    lfo.type = 'square';
    lfo.frequency.value = 30;

### Connecting the graph

The key here is connecting the graph correctly, and also starting both oscillators:

    lfo.connect(amp.gain);
    osc.connect(amp).connect(audioCtx.destination);
    lfo.start();
    osc.start(time);
    osc.stop(time + pulseTime);

**Note**: We also don't have to use the default wave types for either of these oscillators we're creating — we could use a wavetable and the periodic wave method as we did before. There is a multitude of possibilities with just a minimum of nodes.

### Pulse user controls

For the UI controls, let's expose both frequencies of our oscillators, allowing them to be controlled via range inputs. One will change the tone and the other will change how the pulse modulates the first wave:

    <label for="hz">Hz</label>
    <input name="hz" id="hz" type="range" min="660" max="1320" value="880" step="1" />
    <label for="lfo">LFO</label>
    <input name="lfo" id="lfo" type="range" min="20" max="40" value="30" step="1" />

As before, we'll vary the parameters when the range input values are changed by the user.

    let pulseHz = 880;
    const hzControl = document.querySelector('#hz');
    hzControl.addEventListener('input', function() {
        pulseHz = Number(this.value);
    }, false);

    let lfoHz = 30;
    const lfoControl = document.querySelector('#lfo');
    lfoControl.addEventListener('input', function() {
        lfoHz = Number(this.value);
    }, false);

### The final playPulse() function

Here's the entire `playPulse()` function:

    let pulseTime = 1;
    function playPulse(time) {
        let osc = audioCtx.createOscillator();
        osc.type = 'sine';
        osc.frequency.value = pulseHz;

        let amp = audioCtx.createGain();
        amp.gain.value = 1;

        let lfo = audioCtx.createOscillator();
        lfo.type = 'square';
        lfo.frequency.value = lfoHz;

        lfo.connect(amp.gain);
        osc.connect(amp).connect(audioCtx.destination);
        lfo.start();
        osc.start(time);
        osc.stop(time + pulseTime);
    }

The "noise" — random noise buffer with biquad filter
----------------------------------------------------

Now we need to make some noise! All modems have noise. Noise is just random numbers when it comes to audio data, so is, therefore, a relatively straightforward thing to create with code.

### Creating an audio buffer

We need to create an empty container to put these numbers into, however, one that the Web Audio API understands. This is where [`AudioBuffer`](../audiobuffer) objects come in. You can fetch a file and decode it into a buffer (we'll get to that later on in the tutorial), or you can create an empty buffer and fill it with your own data.

For noise, let's do the latter. We first need to calculate the size of our buffer, to create it. We can use the [`BaseAudioContext.sampleRate`](../baseaudiocontext/samplerate) property for this:

    const bufferSize = audioCtx.sampleRate * noiseLength;
    const buffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);

Now we can fill it with random numbers between -1 and 1:

    let data = buffer.getChannelData(0); // get data

    // fill the buffer with noise
    for (let i = 0; i < bufferSize; i++) {
        data[i] = Math.random() * 2 - 1;
    }

**Note**: Why -1 to 1? When outputting sound to a file or speakers we need to have a number to represent 0db full scale — the numerical limit of the fixed point media or DAC. In floating point audio, 1 is a convenient number to map to "full scale" for mathematical operations on signals, so oscillators, noise generators and other sound sources typically output bipolar signals in the range -1 to 1. A browser will clamp values outside this range.

### Creating a buffer source

Now we have the audio buffer and have filled it with data, we need a node to add to our graph that can use the buffer as a source. We'll create a [`AudioBufferSourceNode`](../audiobuffersourcenode) for this, and pass in the data we've created:

    let noise = audioCtx.createBufferSource();
    noise.buffer = buffer;

If we connect this through our audio graph and play it —

    noise.connect(audioCtx.destination);
    noise.start();

you'll notice that it's pretty hissy or tinny. We've created white noise, that's how it should be. Our values are running from -1 to 1, which means we have peaks of all frequencies, which in turn is actually quite dramatic and piercing. We *could* modify the function to run values from 0.5 to -0.5 or similar to take the peaks off and reduce the discomfort, however, where's the fun in that? Let's route the noise we've created through a filter.

### Adding a biquad filter to the mix

We want something in the range of pink or brown noise. We want to cut off those high frequencies and possibly some of the lower ones. Let's pick a bandpass biquad filter for the job.

**Note**: The Web Audio API comes with two types of filter nodes: [`BiquadFilterNode`](../biquadfilternode) and [`IIRFilterNode`](../iirfilternode). For the most part a biquad filter will be good enough — it comes with different types such as lowpass, highpass, and bandpass. If you're looking to do something more bespoke, however, the IIR filter might be a good option — see [Using IIR filters](using_iir_filters) for more information.

Wiring this up is the same as we've seen before. We create the [`BiquadFilterNode`](../biquadfilternode), configure the properties we want for it and connect it through our graph. Different types of biquad filters have different properties — for instance setting the frequency on a bandpass type adjusts the middle frequency, however on a lowpass it would set the top frequency.

    let bandpass = audioCtx.createBiquadFilter();
    bandpass.type = 'bandpass';
    bandpass.frequency.value = 1000;

    // connect our graph
    noise.connect(bandpass).connect(audioCtx.destination);

### Noise user controls

On the UI we'll expose the noise duration and the frequency we want to band, allowing the user to adjust them via range inputs and event handlers just like in previous sections:

    <label for="duration">Duration</label>
    <input name="duration" id="duration" type="range" min="0" max="2" value="1" step="0.1" />

    <label for="band">Band</label>
    <input name="band" id="band" type="range" min="400" max="1200" value="1000" step="5" />

    let noiseDuration = 1;
    const durControl = document.querySelector('#duration');
    durControl.addEventListener('input', function() {
        noiseDuration = Number(this.value);
    }, false);

    let bandHz = 1000;
    const bandControl = document.querySelector('#band');
    bandControl.addEventListener('input', function() {
        bandHz = Number(this.value);
    }, false);

### The final playNoise() function

Here's the entire `playNoise()` function:

    function playNoise(time) {
        const bufferSize = audioCtx.sampleRate * noiseDuration; // set the time of the note
        const buffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate); // create an empty buffer
        let data = buffer.getChannelData(0); // get data

        // fill the buffer with noise
        for (let i = 0; i < bufferSize; i++) {
            data[i] = Math.random() * 2 - 1;
        }

        // create a buffer source for our created data
        let noise = audioCtx.createBufferSource();
        noise.buffer = buffer;

        let bandpass = audioCtx.createBiquadFilter();
        bandpass.type = 'bandpass';
        bandpass.frequency.value = bandHz;

        // connect our graph
        noise.connect(bandpass).connect(audioCtx.destination);
        noise.start(time);
    }

"Dial up" — loading a sound sample
----------------------------------

It's straightforward enough to emulate phone dial (DTMF) sounds, by playing a couple of oscillators together using the methods we've already looked at, however, in this section, we'll load in a sample file instead so we can take a look at what's involved.

### Loading the sample

We want to make sure our file has loaded and been decoded into a buffer before we use it, so let's create an `async` function to allow us to do this:

    async function getFile(audioContext, filepath) {
      const response = await fetch(filepath);
      const arrayBuffer = await response.arrayBuffer();
      const audioBuffer = await audioContext.decodeAudioData(arrayBuffer);
      return audioBuffer;
    }

We can then use the `await` operator when calling this function, which ensures that we can only run subsequent code when it has finished executing.

Let's create another `async` function to set up the sample — we can combine the two async functions in a nice promise pattern to perform further actions when this file is loaded and buffered:

    async function setupSample() {
        const filePath = 'dtmf.mp3';
        const sample = await getFile(audioCtx, filePath);
        return sample;
    }

**Note**: You can easily modify the above function to take an array of files and loop over them to load more than one sample. This would be very handy for more complex instruments, or gaming.

We can now use `setupSample()` like so:

    setupSample()
        .then((sample) => {
            // sample is our buffered file
            // ...
    });

When the sample is ready to play, the program sets up the UI so it is ready to go.

### Playing the sample

Let's create a `playSample()` function in a similar manner to how we did with the other sounds. This time it will create an [`AudioBufferSourceNode`](../audiobuffersourcenode), and put the buffer data we've fetched and decoded into it, and play it:

    function playSample(audioContext, audioBuffer, time) {
        const sampleSource = audioContext.createBufferSource();
        sampleSource.buffer = audioBuffer;
        sampleSource.connect(audioContext.destination)
        sampleSource.start(time);
        return sampleSource;
    }

**Note**: We can call `stop()` on an [`AudioBufferSourceNode`](../audiobuffersourcenode), however, this will happen automatically when the sample has finished playing.

### Dial-up user controls

The [`AudioBufferSourceNode`](../audiobuffersourcenode) comes with a `playbackRate` property. Let's expose that to our UI, so we can speed up and slow down our sample. We'll do that in the same sort of way as before:

    <label for="rate">Rate</label>
    <input name="rate" id="rate" type="range" min="0.1" max="2" value="1" step="0.1" />

    let playbackRate = 1;
    const rateControl = document.querySelector('#rate');
    rateControl.addEventListener('input', function() {
        playbackRate = Number(this.value);
    }, false);

### The final playSample() function

We'll then add a line to update the `playbackRate` property to our `playSample()` function. The final version looks like this:

    function playSample(audioContext, audioBuffer, time) {
        const sampleSource = audioContext.createBufferSource();
        sampleSource.buffer = audioBuffer;
        sampleSource.playbackRate.value = playbackRate;
        sampleSource.connect(audioContext.destination)
        sampleSource.start(time);
        return sampleSource;
    }

**Note**: The sound file was [sourced from soundbible.com](https://soundbible.com/1573-DTMF-Tones.html).

Playing the audio in time
-------------------------

A common problem with digital audio applications is getting the sounds to play in time so that the beat remains consistent, and things do not slip out of time.

We could schedule our voices to play within a `for` loop, however the biggest problem with this is updating whilst it is playing, and we've already implemented UI controls to do so. Also, it would be really nice to consider an instrument-wide BPM control. The best way to get our voices to play on the beat is to create a scheduling system, whereby we look ahead at when the notes are going to play and push them into a queue. We can start them at a precise time with the currentTime property and also take into account any changes.

**Note**: This is a much stripped down version of [Chris Wilson's A Tale Of Two Clocks](https://www.html5rocks.com/en/tutorials/audio/scheduling/) article, which goes into this method in much more detail. There's no point repeating it all here, but it's highly recommended to read this article and use this method. Much of the code here is taken from his [metronome example](https://github.com/cwilso/metronome/blob/master/js/metronome.js), which he references in the article.

Let's start by setting up our default BPM (beats per minute), which will also be user-controllable via — you guessed it — another range input.

    let tempo = 60.0;
    const bpmControl = document.querySelector('#bpm');
    bpmControl.addEventListener('input', function() {
        tempo = Number(this.value);
    }, false);

Then we'll create variables to define how far ahead we want to look, and how far ahead we want to schedule:

    const lookahead = 25.0; // How frequently to call scheduling function (in milliseconds)
    const scheduleAheadTime = 0.1; // How far ahead to schedule audio (sec)

Let's create a function that moves the note forwards by one beat, and loops back to the first when it reaches the 4th (last) one:

    let currentNote = 0;
    let nextNoteTime = 0.0; // when the next note is due.

    function nextNote() {
        const secondsPerBeat = 60.0 / tempo;

        nextNoteTime += secondsPerBeat; // Add beat length to last beat time

        // Advance the beat number, wrap to zero
        currentNote++;
        if (currentNote === 4) {
                currentNote = 0;
        }
    }

We want to create a reference queue for the notes that are to be played, and the functionality to play them using the functions we've previously created:

    const notesInQueue = [];

    function scheduleNote(beatNumber, time) {

        // push the note on the queue, even if we're not playing.
        notesInQueue.push({ note: beatNumber, time: time });

        if (pads[0].querySelectorAll('button')[beatNumber].getAttribute('aria-checked') === 'true') {
            playSweep(time)
        }
        if (pads[1].querySelectorAll('button')[beatNumber].getAttribute('aria-checked') === 'true') {
            playPulse(time)
        }
        if (pads[2].querySelectorAll('button')[beatNumber].getAttribute('aria-checked') === 'true') {
            playNoise(time)
        }
        if (pads[3].querySelectorAll('button')[beatNumber].getAttribute('aria-checked') === 'true') {
            playSample(audioCtx, dtmf, time);
        }
    }

Here we look at the current time and compare it to the time for the next note; when the two match it will call the previous two functions.

[`AudioContext`](../audiocontext) object instances have a `currentTime` property, which allows us to retrieve the number of seconds after we first created the context. This is what we shall use for timing within our step sequencer — It's extremely accurate, returning a float value accurate to about 15 decimal places.

    function scheduler() {
        // while there are notes that will need to play before the next interval, schedule them and advance the pointer.
        while (nextNoteTime < audioCtx.currentTime + scheduleAheadTime ) {
            scheduleNote(currentNote, nextNoteTime);
            nextNote();
        }
        timerID = window.setTimeout(scheduler, lookahead);
    }

We also need a draw function to update the UI, so we can see when the beat progresses.

    let lastNoteDrawn = 3;

    function draw() {
        let drawNote = lastNoteDrawn;
        let currentTime = audioCtx.currentTime;

        while (notesInQueue.length && notesInQueue[0].time < currentTime) {
            drawNote = notesInQueue[0].note;
            notesInQueue.splice(0,1);   // remove note from queue
        }

        // We only need to draw if the note has moved.
        if (lastNoteDrawn != drawNote) {
            pads.forEach(function(el, i) {
                el.children[lastNoteDrawn].style.borderColor = 'hsla(0, 0%, 10%, 1)';
                el.children[drawNote].style.borderColor = 'hsla(49, 99%, 50%, 1)';
            });

            lastNoteDrawn = drawNote;
        }
        // set up to draw again
        requestAnimationFrame(draw);
    }

Putting it all together
-----------------------

Now all that's left to do is make sure we've loaded the sample before we are able to *play* the instrument. We'll add a loading screen that disappears when the file has been fetched and decoded, then we can allow the scheduler to start using the play button click event.

    // when the sample has loaded allow play
    let loadingEl = document.querySelector('.loading');
    const playButton = document.querySelector('[data-playing]');
    let isPlaying = false;
    setupSample()
        .then((sample) => {
            loadingEl.style.display = 'none'; // remove loading screen

            dtmf = sample; // to be used in our playSample function

            playButton.addEventListener('click', function() {
                isPlaying = !isPlaying;

                if (isPlaying) { // start playing

                    // check if context is in suspended state (autoplay policy)
                    if (audioCtx.state === 'suspended') {
                        audioCtx.resume();
                    }

                    currentNote = 0;
                    nextNoteTime = audioCtx.currentTime;
                    scheduler(); // kick off scheduling
                    requestAnimationFrame(draw); // start the drawing loop.
                    this.dataset.playing = 'true';

                } else {

                    window.clearTimeout(timerID);
                    this.dataset.playing = 'false';

                }
            })
        });

Summary
-------

We've now got an instrument inside our browser! Keep playing and experimenting — you can expand on any of these techniques to create something much more elaborate.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Advanced_techniques" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Advanced_techniques</a>
