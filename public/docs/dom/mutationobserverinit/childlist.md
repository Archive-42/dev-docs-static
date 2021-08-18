MutationObserverInit.childList
==============================

The **[`MutationObserverInit`](../mutationobserverinit)** dictionary's optional `childList` property indicates whether or not to monitor the specified node or nodes for the addition or removal of new child nodes.

If `childList` is `false` (the default), adding or removing new nodes does not trigger mutation callbacks. By setting `childList` to `true`, your callback will be invoked any time nodes are added to or removed from the DOM node or nodes being watched.

Syntax
------

    var options = {
      childList: true | false
    }

### Value

A Boolean value indicating whether or not to invoke the callback function when new nodes are added to or removed from the section of the DOM being monitored.. If [`subtree`](subtree) is `false`, only the node indicated by the observer's target node is monitored for changes. Setting `subtree` to `true` causes addition or removal of nodes anywhere within the subtree rooted at `target` to be reported.

Example
-------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserverinit-childlist">DOM<br />
<span class="small">The definition of 'MutationObserverInit.childList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`childList`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/childList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/childList</a>
