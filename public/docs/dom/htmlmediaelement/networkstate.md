HTMLMediaElement.networkState
=============================

The `HTMLMediaElement.networkState` property indicates the current state of the fetching of media over the network.

Syntax
------

    var networkState = audioOrVideo.networkState;

### Value

An `unsigned short`. Possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NETWORK_EMPTY</code></td><td>0</td><td>There is no data yet. Also, <code>readyState</code> is <code>HAVE_NOTHING</code>.</td></tr><tr class="even"><td><code>NETWORK_IDLE</code></td><td>1</td><td>HTMLMediaElement is active and has selected a resource, but is not using the network.</td></tr><tr class="odd"><td><code>NETWORK_LOADING</code></td><td>2</td><td>The browser is downloading HTMLMediaElement data.</td></tr><tr class="even"><td><code>NETWORK_NO_SOURCE</code></td><td>3</td><td>No HTMLMediaElement src found.</td></tr></tbody></table>

Examples
--------

This example will listen for the audio element to begin playing and then check if it is still loading data.

    <audio id="example" preload="auto">
     <source src="sound.ogg" type="audio/ogg" />
    </audio>

    var obj = document.getElementById('example');

    obj.addEventListener('playing', function() {

      if (obj.networkState === 2) {
        // Still loading...
      }

    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-networkstate">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.networkState' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.networkState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`networkState`

43

12

3.5

The `NETWORK_LOADED` state was removed to align with the HTML spec in Firefox 4.

9

≤12.1

3.1

Yes

Yes

4

≤12.1

2

Yes

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/networkState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/networkState</a>
