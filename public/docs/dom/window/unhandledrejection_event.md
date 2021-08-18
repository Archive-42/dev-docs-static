Window: unhandledrejection event
================================

The `unhandledrejection` event is sent to the global scope of a script when a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that has no rejection handler is rejected; typically, this is the [`window`](../window), but may also be a [`Worker`](../worker). This is useful for debugging and for providing fallback error handling for unexpected situations.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../promiserejectionevent"><code>PromiseRejectionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../windoweventhandlers/onunhandledrejection"><code>onunhandledrejection</code></a></td></tr></tbody></table>

Usage notes
-----------

Allowing the `unhandledrejection` event to bubble will eventually result in an error message being output to the console. You can prevent this by calling [`preventDefault()`](../event/preventdefault) on the [`PromiseRejectionEvent`](../promiserejectionevent); see [Preventing default handling](#preventing_default_handling) below for an example.

Examples
--------

Here we have a few examples showing ways you can make use of the `unhandledrejection` event. The event includes two useful pieces of information:

`promise`  
The actual [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which was rejected with no handler available to deal with the rejection.

`reason`  
The reason that would have been passed into the rejection handler if one had existed. See [`catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) for details.

### Basic error logging

This example logs information about the unhandled promise rejection to the console.

    window.addEventListener("unhandledrejection", event => {
      console.warn(`UNHANDLED PROMISE REJECTION: ${event.reason}`);
    });

You can also use the [`onunhandledrejection`](../windoweventhandlers/onunhandledrejection) event handler property to set up the event listener:

    window.onunhandledrejection = event => {
      console.warn(`UNHANDLED PROMISE REJECTION: ${event.reason}`);
    };

### Preventing default handling

Many environments (such as [Node.js](https://developer.mozilla.org/en-US/docs/Glossary/Node.js)) report unhandled promise rejections to the console by default. You can prevent that from happening by adding a handler for `unhandledrejection` events that—in addition to any other tasks you wish to perform—calls [`preventDefault()`](../event/preventdefault) to cancel the event, preventing it from bubbling up to be handled by the runtime's logging code. This works because `unhandledrejection` is cancelable.

    window.addEventListener('unhandledrejection', function (event) {
      // ...your code here to handle the unhandled rejection...

      // Prevent the default handling (such as outputting the
      // error to the console)

      event.preventDefault();
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#unhandled-promise-rejections">HTML Living Standard<br />
<span class="small">The definition of 'unhandledrejection' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`unhandledrejection_event`

49

79

69

68

No

36

11

49

49

68

36

11.3

5.0

See also
--------

-   [Promise rejection events](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#promise_rejection_events) in [Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
-   [`onunhandledrejection`](../windoweventhandlers/onunhandledrejection) event handler property<sup>[1](#seealso-footnote-1)</sup>
-   [`rejectionhandled`](rejectionhandled_event) event
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

<span id="seealso-footnote-1">\[1\]</span> The corresponding event handler property is defined on the [`WindowEventHandlers`](../windoweventhandlers) mixin, which is available on both the [`Window`](../window) interface and all types of [`Worker`](../worker) interfaces.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/unhandledrejection_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/unhandledrejection_event</a>
