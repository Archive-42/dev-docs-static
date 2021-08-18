Selection.containsNode()
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.containsNode()` method indicates whether a specfied node is part of the selection.

Syntax
------

    sel.containsNode(node, partialContainment)

### Parameters

`node`  
The node that is being looked for in the selection.

 `partialContainment` <span class="badge inline optional">Optional</span>   
When `true`, `containsNode()` returns `true` when a part of the node is part of the selection. When `false`, `containsNode()` only returns `true` when the entire node is part of the selection. If not specified, the default value `false` is used.

Example
-------

### Check for selection

This snippet checks whether anything inside the body element is selected.

    console.log(window.getSelection().containsNode(document.body, true));

### Find the hidden word

In this example, a message appears when you select the secret word. It uses [`addEventListener()`](../eventtarget/addeventlistener) to check for [`selectionchange`](../document/selectionchange_event) events.

#### HTML

    <p>Can you find the secret word?</p>
    <p>Hmm, where <span id="secret" style="color:transparent">SECRET</span> could it be?</p>
    <p id="win" hidden>You found it!</p>

#### JavaScript

    const secret = document.getElementById('secret');
    const win = document.getElementById('win');

    // Listen for selection changes
    document.addEventListener('selectionchange', () => {
      const selection = window.getSelection();
      const found = selection.containsNode(secret);

      win.toggleAttribute('hidden', !found);
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-containsnode">Selection API<br />
<span class="small">The definition of 'Selection.containsNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`containsNode`

1

12

1

Before Firefox 35, the method didn't throw if `node` was `null`.

No

≤12.1

3.1

1

18

4

Before Firefox 35, the method didn't throw if `node` was `null`.

≤12.1

2

1.0

`partialContainment`

Yes

≤79

55

No

Yes

Yes

Yes

Yes

55

Yes

Yes

Yes

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/containsNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/containsNode</a>
