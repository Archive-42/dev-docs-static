Controlling multiple parameters with ConstantSourceNode
=======================================================

This article demonstrates how to use a [`ConstantSourceNode`](../constantsourcenode) to link multiple parameters together so they share the same value, which can be changed by setting the value of the [`ConstantSourceNode.offset`](../constantsourcenode/offset) parameter.

You may have times when you want to have multiple audio parameters be linked so they share the same value even while being changed in some way. For example, perhaps you have a set of oscillators, and two of them need to share the same, configurable volume, or you have a filter that's been applied to certain inputs but not to all of them. You could use a loop and change the value of each affected [`AudioParam`](../audioparam) one at a time, but there are two drawbacks to doing it that way: first, that's extra code that, as you're about to see, you don't have to write; and second, that loop uses valuable CPU time on your thread (likely the main thread), and there's a way to offload all that work to the audio rendering thread, which is optimized for this kind of work and may run at a more appropriate priority level than your code.

The solution is simple, and it involves using an audio node type which, at first glance, doesn't look all that useful: [`ConstantSourceNode`](../constantsourcenode).

The technique
-------------

This is actually a really easy way to do something that sounds like it might be hard to do. You need to create a [`ConstantSourceNode`](../constantsourcenode) and connect it to all of the [`AudioParam`](../audioparam)s whose values should be linked to always match each other. Since `ConstantSourceNode`'s [`offset`](../constantsourcenode/offset) value is sent straight through to all of its outputs, it acts as a splitter for that value, sending it to each connected parameter.

The diagram below shows how this works; an input value, `N`, is set as the value of the [`ConstantSourceNode.offset`](../constantsourcenode/offset) property. The `ConstantSourceNode` can have as many outputs as necessary; in this case, we've connected it to three nodes: two [`GainNode`](../gainnode)s and a [`StereoPannerNode`](../stereopannernode). So `N` becomes the value of the specified parameter ([`gain`](../gainnode/gain) for the [`GainNode`](../gainnode)s and pan for the [`StereoPannerNode`](../stereopannernode).

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjcgNyA1ODAgMzQ2IiB3aWR0aD0iNTgwcHQiIGhlaWdodD0iMzQ2cHQiPjxkZWZzPjxtYXJrZXIgb3JpZW50PSJhdXRvIiBvdmVyZmxvdz0idmlzaWJsZSIgbWFya2VyVW5pdHM9InN0cm9rZVdpZHRoIiBpZD0iYSIgdmlld0JveD0iLTEgLTMgNyA2IiBtYXJrZXJXaWR0aD0iNyIgbWFya2VySGVpZ2h0PSI2IiBjb2xvcj0iIzAwMCI+PHBhdGggZD0iTTQuOCAwIDAtMS44djMuNnoiIGZpbGw9ImN1cnJlbnRDb2xvciIgc3Ryb2tlPSJjdXJyZW50Q29sb3IiLz48L21hcmtlcj48L2RlZnM+PGcgZmlsbD0ibm9uZSI+PHBhdGggZmlsbD0iIzg2N2ZmZiIgZD0iTTIwNyA5OWgxODB2NDVIMjA3eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMjA3IDk5aDE4MHY0NUgyMDd6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMjEyIDExMykiIGZpbGw9IiMwMDAiPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjUwMCIgeD0iOS4zODgiIHk9IjE0IiB0ZXh0TGVuZ3RoPSIxNTEuMjI1Ij5Db25zdGFudFNvdXJjZU5vZGU8L3RzcGFuPjwvdGV4dD48cGF0aCBmaWxsPSIjODY3ZmZmIiBkPSJNOSAyMTZoMTgwdjQ1SDl6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik05IDIxNmgxODB2NDVIOXoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNCAyMzApIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIiIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI1MDAiIHg9IjUxLjM5NSIgeT0iMTQiIHRleHRMZW5ndGg9IjY3LjIxMSI+R2Fpbk5vZGU8L3RzcGFuPjwvdGV4dD48cGF0aCBmaWxsPSIjODY3ZmZmIiBkPSJNNDA1IDIxNmgxODB2NDVINDA1eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNNDA1IDIxNmgxODB2NDVINDA1eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDQxMCAyMzApIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIiIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI1MDAiIHg9IjUxLjM5NSIgeT0iMTQiIHRleHRMZW5ndGg9IjY3LjIxMSI+R2Fpbk5vZGU8L3RzcGFuPjwvdGV4dD48cGF0aCBmaWxsPSIjODY3ZmZmIiBkPSJNMjA3IDIxNmgxODB2NDVIMjA3eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMjA3IDIxNmgxODB2NDVIMjA3eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDIxMiAyMzApIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIiIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI1MDAiIHg9IjE3Ljc4OSIgeT0iMTQiIHRleHRMZW5ndGg9IjEzNC40MjIiPlN0ZXJlb1Bhbm5lck5vZGU8L3RzcGFuPjwvdGV4dD48cGF0aCBkPSJNMjUyIDE0NHYyN0g5OXYzMi4xTTI5NyAxNDR2NTkuMW00NS01OS4xdjI3aDE1M3YzMi4xIiBtYXJrZXItZW5kPSJ1cmwoI2EpIiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIi8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNTUuODc2IDE5Mi40NDcpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIiIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI1MDAiIHg9Ii4xOTciIHk9IjE0IiB0ZXh0TGVuZ3RoPSIzMy42MDUiPmdhaW48L3RzcGFuPjwvdGV4dD48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyNTguNjQgMTkyLjg1NCkiIGZpbGw9IiMwMDAiPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjUwMCIgeD0iLjM5OCIgeT0iMTQiIHRleHRMZW5ndGg9IjI1LjIwNCI+cGFuPC90c3Bhbj48L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNTA0LjM3IDE5My4zNDcpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIiIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI1MDAiIHg9Ii4xOTciIHk9IjE0IiB0ZXh0TGVuZ3RoPSIzMy42MDUiPmdhaW48L3RzcGFuPjwvdGV4dD48cGF0aCBtYXJrZXItZW5kPSJ1cmwoI2EpIiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIiBkPSJNMjk3IDU0djMyLjEiLz48cGF0aCBkPSJNMjQzIDloMTQ0bC0zNiA0NUgyMDd6IiBmaWxsPSIjZmZmIi8+PHBhdGggZD0iTTI0MyA5aDE0NGwtMzYgNDVIMjA3eiIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyNDggMjIpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNTAwIiB4PSIxNy43MzQiIHk9IjE1IiB0ZXh0TGVuZ3RoPSI1Mi45MyI+aW5wdXQgPSA8L3RzcGFuPjx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciIgZm9udC1zaXplPSIxNiIgZm9udC1zdHlsZT0iaXRhbGljIiBmb250LXdlaWdodD0iNTAwIiB4PSI3MC42NjQiIHk9IjE1IiB0ZXh0TGVuZ3RoPSI5LjYwMiI+TjwvdHNwYW4+PC90ZXh0PjxwYXRoIGQ9Ik0yNDMgMzA2aDE0NGwtMzYgNDVIMjA3eiIgZmlsbD0iI2ZmZiIvPjxwYXRoIGQ9Ik0yNDMgMzA2aDE0NGwtMzYgNDVIMjA3eiIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyNDggMzE5KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxNiIgZm9udC13ZWlnaHQ9IjUwMCIgeD0iMTIuODQiIHk9IjE1IiB0ZXh0TGVuZ3RoPSI2Mi43MTkiPm91dHB1dCA9IDwvdHNwYW4+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIiBmb250LXNpemU9IjE2IiBmb250LXN0eWxlPSJpdGFsaWMiIGZvbnQtd2VpZ2h0PSI1MDAiIHg9Ijc1LjU1OSIgeT0iMTUiIHRleHRMZW5ndGg9IjkuNjAyIj5OPC90c3Bhbj48L3RleHQ+PHBhdGggbWFya2VyLWVuZD0idXJsKCNhKSIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0ibTI5Ni41IDI2MSAuMzU3IDMyLjEwMSIvPjxwYXRoIGQ9Ik00NDEgMzA2aDE0NGwtMzYgNDVINDA1eiIgZmlsbD0iI2ZmZiIvPjxwYXRoIGQ9Ik00NDEgMzA2aDE0NGwtMzYgNDVINDA1eiIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg0NDYgMzE5KSIgZmlsbD0iIzAwMCI+PHRzcGFuIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxNiIgZm9udC13ZWlnaHQ9IjUwMCIgeD0iMTIuODQiIHk9IjE1IiB0ZXh0TGVuZ3RoPSI2Mi43MTkiPm91dHB1dCA9IDwvdHNwYW4+PHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIiBmb250LXNpemU9IjE2IiBmb250LXN0eWxlPSJpdGFsaWMiIGZvbnQtd2VpZ2h0PSI1MDAiIHg9Ijc1LjU1OSIgeT0iMTUiIHRleHRMZW5ndGg9IjkuNjAyIj5OPC90c3Bhbj48L3RleHQ+PHBhdGggbWFya2VyLWVuZD0idXJsKCNhKSIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTQ5NSAyNjF2MzIuMSIvPjxwYXRoIGQ9Ik00NSAzMDZoMTQ0bC0zNiA0NUg5eiIgZmlsbD0iI2ZmZiIvPjxwYXRoIGQ9Ik00NSAzMDZoMTQ0bC0zNiA0NUg5eiIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg1MCAzMTkpIiBmaWxsPSIjMDAwIj48dHNwYW4gZm9udC1mYW1pbHk9IkFyaWFsIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNTAwIiB4PSIxMi44NCIgeT0iMTUiIHRleHRMZW5ndGg9IjYyLjcxOSI+b3V0cHV0ID0gPC90c3Bhbj48dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIiIGZvbnQtc2l6ZT0iMTYiIGZvbnQtc3R5bGU9Iml0YWxpYyIgZm9udC13ZWlnaHQ9IjUwMCIgeD0iNzUuNTU5IiB5PSIxNSIgdGV4dExlbmd0aD0iOS42MDIiPk48L3RzcGFuPjwvdGV4dD48cGF0aCBtYXJrZXItZW5kPSJ1cmwoI2EpIiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIiBkPSJNOTkgMjYxdjMyLjEiLz48L2c+PC9zdmc+" alt="Dagram in SVG showing how ConstantSourceNode can be used to split an input parameter to share it with multiple nodes." width="773" height="461" />

As a result, every time you change `N` (the value of the input [`AudioParam`](../audioparam), the values of the two `GainNode`s' `gain` properties and the value of the `StereoPannerNode`'s `pan` propertry are all set to `N` as well.

Example
-------

Let's take a look at this technique in action. In this simple example, we create three [`OscillatorNode`](../oscillatornode)s. Two of them have adjustable gain, controlled using a shared input control. The other oscillator has a fixed volume.

### HTML

The HTML content for this example is primarily a button to toggle the oscillator tones on and off and an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element of type `range` to control the volume of two of the three oscillators.

    <div class="controls">
      <div class="left">
        <div id="playButton" class="button">
          ▶️
        </div>
      </div>
      <div class="right">
        <span>Volume: </span>
        <input type="range" min="0.0" max="1.0" step="0.01"
            value="0.8" name="volume" id="volumeControl">
      </div>
    </div>

    <p>Use the button above to start and stop the tones, and the volume control to
    change the volume of the notes E and G in the chord.</p>

### JavaScript

Now let's take a look at the JavaScript code, a piece at a time.

#### Setting up

Let's start by looking at the global variable initialization.

    let context = null;

    let playButton = null;
    let volumeControl = null;

    let oscNode1 = null;
    let oscNode2 = null;
    let oscNode3 = null;
    let constantNode = null;
    let gainNode1 = null;
    let gainNode2 = null;
    let gainNode3 = null;

    let playing = false;

These variables are:

`context`  
The [`AudioContext`](../audiocontext) in which all the audio nodes live.

 `playButton` and `volumeControl`   
References to the play button and volume control elements.

 `oscNode1`, `oscNode2`, and `oscNode3`   
The three [`OscillatorNode`](../oscillatornode)s used to generate the chord.

 `gainNode1`, `gainNode2`, and `gainNode3`   
The three [`GainNode`](../gainnode) instances which provide the volume levels for each of the three oscillators. `gainNode2` and `gainNode3` will be linked together to have the same, adjustable, value using the [`ConstantSourceNode`](../constantsourcenode).

`constantNode`  
The [`ConstantSourceNode`](../constantsourcenode) used to control the values of `gainNode2` and `gainNode3` together.

`playing`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that we'll use to keep track of whether or not we're currently playing the tones.

Now let's look at the `setup()` function, which is our handler for the window's `load` event; it handles all the initialization tasks that require the DOM to be in place.

    function setup() {
      context = new (window.AudioContext || window.webkitAudioContext)();

      playButton = document.querySelector("#playButton");
      volumeControl = document.querySelector("#volumeControl");

      playButton.addEventListener("click", togglePlay, false);
      volumeControl.addEventListener("input", changeVolume, false);

      gainNode1 = context.createGain();
      gainNode1.gain.value = 0.5;

      gainNode2 = context.createGain();
      gainNode3 = context.createGain();
      gainNode2.gain.value = gainNode1.gain.value;
      gainNode3.gain.value = gainNode1.gain.value;
      volumeControl.value = gainNode1.gain.value;

      constantNode = context.createConstantSource();
      constantNode.connect(gainNode2.gain);
      constantNode.connect(gainNode3.gain);
      constantNode.start();

      gainNode1.connect(context.destination);
      gainNode2.connect(context.destination);
      gainNode3.connect(context.destination);
    }

    window.addEventListener("load", setup, false);

First, we get access to the window's [`AudioContext`](../audiocontext), stashing the reference in `context`. Then we get references to the control widgets, setting `playButton` to reference the play button and `volumeControl` to reference the slider control that the user will use to adjust the gain on the linked pair of oscillators.

Then we assign a handler for the play button's `click` event (see [Toggling the oscillators on and off](#toggling_the_oscillators_on_and_off) for more on the `togglePlay()` method), and for the volume slider's `input` event (see [Controlling the linked oscillators](#controlling_the_linked_oscillators) to see the very short `changeVolume()` method).

Next, the [`GainNode`](../gainnode) `gainNode1` is created to handle the volume for the non-linked oscillator (`oscNode1`). We set that gain to 0.5. We also create `gainNode2` and `gainNode3`, setting their values to match `gainNode1`, then set the value of the volume slider to the same value, so it is synchronized with the gain level it controls.

Once all the gain nodes are created, we create the [`ConstantSourceNode`](../constantsourcenode), `constantNode`. We connect its output to the `gain` [`AudioParam`](../audioparam) on both `gainNode2` and `gainNode3`, and we start the constant node running by calling its [`start()`](../audioscheduledsourcenode/start) method; now it's sending the value 0.5 to the two gain nodes' values, and any change to [`constantNode.offset`](../constantsourcenode/offset) will automatically set the gain of both `gainNode2` and `gainNode3` (affecting their audio inputs as expected).

Finally, we connect all the gain nodes to the [`AudioContext`](../audiocontext)'s [`destination`](../baseaudiocontext/destination), so that any sound delivered to the gain nodes will reach the output, whether that output be speakers, headphones, a recording stream, or any other destination type.

After setting the window's `load` event handler to be the `setup()` function, the stage is set. Let's see how the action plays out.

#### Toggling the oscillators on and off

Because [`OscillatorNode`](../oscillatornode) doesn't support the notion of being in a paused state, we have to simulate it by terminating the oscillators and starting them again when the play button is clicked again to toggle them back on. Let's look at the code.

    function togglePlay(event) {
      if (playing) {
        playButton.textContent = "▶️";
        stopOscillators();
      } else {
        playButton.textContent = "⏸";
        startOscillators();
      }
    }

If the `playing` variable indicates we're already playing the oscillators, we change the `playButton`'s content to be the Unicode character "right-pointing triangle" (▶️) and call `stopOscillators()` to shut down the oscillators. See [Stopping the oscillators](#stopping_the_oscillators) below for that code.

If `playing` is false, indicating that we're currently paused, we change the play button's content to be the Unicode character "pause symbol" (⏸) and call `startOscillators()` to start the oscillators playing their tones. That code is covered under [Starting the oscillators](#starting_the_oscillators) below.

#### Controlling the linked oscillators

The `changeVolume()` function—the event handler for the slider control for the gain on the linked oscillator pair—looks like this:

    function changeVolume(event) {
      constantNode.offset.value = volumeControl.value;
    }

That simple function controls the gain on both nodes. All we have to do is set the value of the [`ConstantSourceNode`](../constantsourcenode)'s [`offset`](../constantsourcenode/offset) parameter. That value becomes the node's constant output value, which is fed into all of its outputs, which are, as set above, `gainNode2` and `gainNode3`.

While this is an extremely simple example, imagine having a 32 oscillator synthesizer with multiple linked parameters in play across a number of patched nodes. Being able to shorten the number of operations to adjust them all will prove invaluable for code size and performance both.

#### Starting the oscillators

When the user clicks the play/pause toggle button while the oscillators aren't playing, the `startOscillators()` function gets called.

    function startOscillators() {
      oscNode1 = context.createOscillator();
      oscNode1.type = "sine";
      oscNode1.frequency.value = 261.625565300598634; // middle C
      oscNode1.connect(gainNode1);

      oscNode2 = context.createOscillator();
      oscNode2.type = "sine";
      oscNode2.frequency.value = 329.627556912869929; // E
      oscNode2.connect(gainNode2);

      oscNode3 = context.createOscillator();
      oscNode3.type = "sine";
      oscNode3.frequency.value = 391.995435981749294 // G
      oscNode3.connect(gainNode3);

      oscNode1.start();
      oscNode2.start();
      oscNode3.start();

      playing = true;
    }

Each of the three oscillators is set up the same way:

1.  Create the [`OscillatorNode`](../oscillatornode) by calling [`BaseAudioContext.createOscillator`](../baseaudiocontext/createoscillator).
2.  Set the oscillator's type to `"sine"` to use a sine wave as the audio waveform.
3.  Set the oscillator's frequency to the desired value; in this case, `oscNode1` is set to a middle C, while `oscNode2` and `oscNode3` round out the chord by playing the E and G notes.
4.  Connect the new oscillator to the corresponding gain node.

Once all three oscillators have been created, they're started by calling each one's [`ConstantSourceNode.start()`](../audioscheduledsourcenode/start) method in turn, and `playing` is set to `true` to track that the tones are playing.

#### Stopping the oscillators

Stopping the oscillators when the user toggles the play state to pause the tones is as simple as stopping each node.

    function stopOscillators() {
      oscNode1.stop();
      oscNode2.stop();
      oscNode3.stop();
      playing = false;
    }

Each node is stopped by calling its [`ConstantSourceNode.stop()`](../audioscheduledsourcenode/stop) method, then `playing` is set to `false`.

### Result

See also
--------

-   [Web Audio API](../web_audio_api)
-   [Using the Web Audio API](using_web_audio_api)
-   [Simple synth keyboard](simple_synth) (example)
-   [`OscillatorNode`](../oscillatornode)
-   [`ConstantSourceNode`](../constantsourcenode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode</a>
