MutationObserver
================

The [`MutationObserver`](mutationobserver) interface provides the ability to watch for changes being made to the [DOM](document_object_model) tree. It is designed as a replacement for the older [Mutation Events](mutationevent) feature, which was part of the DOM3 Events specification.

Constructor
-----------

[`MutationObserver()`](mutationobserver/mutationobserver)  
Creates and returns a new `MutationObserver` which will invoke a specified callback function when DOM changes occur.

Methods
-------

[`disconnect()`](mutationobserver/disconnect)  
Stops the `MutationObserver` instance from receiving further notifications until and unless [`observe()`](mutationobserver/observe) is called again.

[`observe()`](mutationobserver/observe)  
Configures the `MutationObserver` to begin receiving notifications through its callback function when DOM changes matching the given options occur.

[`takeRecords()`](mutationobserver/takerecords)  
Removes all pending notifications from the `MutationObserver`'s notification queue and returns them in a new [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`MutationRecord`](mutationrecord) objects.

Mutation Observer & customize resize event listener & demo
----------------------------------------------------------

<https://codepen.io/webgeeker/full/YjrZgg/>

Example
-------

The following example was adapted from [this blog post](https://hacks.mozilla.org/2012/05/dom-mutationobserver-reacting-to-dom-changes-without-killing-browser-performance/).

    // Select the node that will be observed for mutations
    const targetNode = document.getElementById('some-id');

    // Options for the observer (which mutations to observe)
    const config = { attributes: true, childList: true, subtree: true };

    // Callback function to execute when mutations are observed
    const callback = function(mutationsList, observer) {
        // Use traditional 'for loops' for IE 11
        for(const mutation of mutationsList) {
            if (mutation.type === 'childList') {
                console.log('A child node has been added or removed.');
            }
            else if (mutation.type === 'attributes') {
                console.log('The ' + mutation.attributeName + ' attribute was modified.');
            }
        }
    };

    // Create an observer instance linked to the callback function
    const observer = new MutationObserver(callback);

    // Start observing the target node for configured mutations
    observer.observe(targetNode, config);

    // Later, you can stop observing
    observer.disconnect();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-mutationobserver">DOM<br />
<span class="small">The definition of 'MutationObserver' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`MutationObserver`

26

18

12

14

11

15

7

6

≤37

≤37

26

18

14

14

7

6

1.5

1.0

`MutationObserver`

26

18

12

14

11

15

7

6

≤37

≤37

26

18

14

14

7

6

1.5

1.0

`disconnect`

18

12

14

11

15

6

≤37

18

14

14

6

1.0

`observe`

18

12

14

11

15

6

≤37

18

14

14

6

1.0

`takeRecords`

18

12

14

11

15

6

≤37

18

14

14

6

1.0

See also
--------

-   [`PerformanceObserver`](performanceobserver)
-   [`ResizeObserver`](resizeobserver)
-   [`IntersectionObserver`](intersectionobserver)
-   [A brief overview](https://updates.html5rocks.com/2012/02/Detect-DOM-changes-with-Mutation-Observers)
-   [A more in-depth discussion](https://hacks.mozilla.org/2012/05/dom-mutationobserver-reacting-to-dom-changes-without-killing-browser-performance/)
-   [A screencast by Chromium developer Rafael Weinstein](https://www.youtube.com/watch?v=eRZ4pO0gVWw)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver</a>
