MutationObserver.takeRecords()
==============================

The [`MutationObserver`](../mutationobserver) method `takeRecords()` returns a list of all matching DOM changes that have been detected but not yet processed by the observer's callback function, leaving the mutation queue empty. The most common use case for this is to immediately fetch all pending mutation records immediately prior to disconnecting the observer, so that any pending mutations can be processed when stopping down the observer.

Syntax
------

    const mutationRecords = mutationObserver.takeRecords()

### Parameters

None.

### Return value

An array [`MutationRecord`](../mutationrecord) objects, each describing one change applied to the observed portion of the document's DOM tree.

**Note:** The queue of mutations which have occurred, but not been delivered to the observer's callback is left empty after calling `takeRecords()`.

Example
-------

In this example, we demonstrate how to handle any undelivered [`MutationRecord`](../mutationrecord)s by calling `takeRecords()` just before disconnecting the observer.

    const targetNode = document.querySelector("#someElement");
    const observerOptions = {
      childList: true,
      attributes: true
    }

    const observer = new MutationObserver(callback);
    observer.observe(targetNode, observerOptions);

    /* ...later, when it's time to stop observing... */

    /* handle any still-pending mutations */

    let mutations = observer.takeRecords();

    observer.disconnect();

    if (mutations) {
      callback(mutations);
    }

The code in lines 12–17 fetches any unprocessed mutation records, then invokes the callback with the records so that they can be processed. This is done immediately prior to calling [`disconnect()`](disconnect) to stop observing the DOM.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserver-takerecords">DOM<br />
<span class="small">The definition of 'MutationObserver.takeRecords()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/takeRecords" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/takeRecords</a>
