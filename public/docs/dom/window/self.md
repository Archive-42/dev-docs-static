Window.self
===========

The `Window.self` read-only property returns the window itself, as a <span class="page-not-created">`WindowProxy`</span>. It can be used with dot notation on a `window` object (that is, `window.self`) or standalone (`self`). The advantage of the standalone notation is that a similar notation exists for non-window contexts, such as in [Web Workers](../worker). By using `self`, you can refer to the global scope in a way that will work not only in a window context (`self` will resolve to `window.self`) but also in a worker context (`self` will then resolve to [`WorkerGlobalScope.self`](../workerglobalscope/self)).

Example
-------

Uses of `window.self` like the following could just as well be replaced by `window`.

    if (window.parent.frames[0] != window.self) {
        // this window is not the first frame in the list
    }

Furthermore, when executing in the active document of a browsing context, `window` is a reference to the current global object and thus all of the following are equivalent:

    var w1 = window;
    var w2 = self;
    var w3 = window.window;
    var w4 = window.self;
    // w1, w2, w3, w4 all strictly equal, but only w2 will function in workers

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-self">HTML Living Standard<br />
<span class="small">The definition of 'Window.self' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No difference from the latest snapshot <a href="https://www.w3.org/TR/html51/">HTML 5.1</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/browsers.html#dom-self">HTML 5.1<br />
<span class="small">The definition of 'Window.self' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No difference from the <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-self">HTML5<br />
<span class="small">The definition of 'Window.self' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>First snapshot containing the definition of <code>Window.self</code>.</td></tr></tbody></table>

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

`self`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   Its `Worker` equivalent, [`WorkerGlobalScope.self`](../workerglobalscope/self).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/self" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/self</a>
