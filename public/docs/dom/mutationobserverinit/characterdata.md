MutationObserverInit.characterData
==================================

The **[`MutationObserverInit`](../mutationobserverinit)** dictionary's optional `characterData` property is used to specify whether or not to monitor the node or nodes being observed for changes to their textual contents.

Character data changes are detectable on any text node, including nodes based on the [`Text`](../text), [`ProcessingInstruction`](../processinginstruction), and [`Comment`](../comment) interfaces.

Note that this doesn't monitor content of an [`HTMLElement`](../htmlelement), even if it only contains text inside, as it only monitors text nodes themselves. So either pass directly a text node to the [`observe()`](../mutationobserver/observe) method or you need to also set `subtree: true`.

Syntax
------

    var options = {
      characterData: true | false
    }

### Value

A Boolean value indicating whether or not to call the observer's callback function when textual nodes' values change.

If `true`, the callback specified when [`observe()`](../mutationobserver/observe) was used to start observing the node or subtree is called any time the contents of a text node are changed.

You can expand the capabilities of attribute mutation monitoring using other options:

-   [`characterDataOldValue`](characterdataoldvalue) lets you specify whether or not you want the previous value of changed text nodes to be provided using the [`MutationRecord`](../mutationrecord)'s <span class="page-not-created">`oldValue`</span> property.
-   [`subtree`](subtree) lets you specify whether to watch the target node and all of its descendants (`true`), or just the target node (`false`).

If you set `characterDataOldValue` to `true`, `characterData` is automatically assumed to be `true`, even if you don't expressly set it as such.

Example
-------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserverinit-characterdata">DOM<br />
<span class="small">The definition of 'MutationObserverInit.characterData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`characterData`

18

12

14

Starting in Firefox 36, `characterData` has no default value; previously, its default value was `false`.

11

15

6

≤37

18

14

Starting in Firefox 36, `characterData` has no default value; previously, its default value was `false`.

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/characterData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/characterData</a>
