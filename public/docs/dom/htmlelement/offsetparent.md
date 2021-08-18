HTMLElement.offsetParent
========================

The `HTMLElement.offsetParent` read-only property returns a reference to the element which is the closest (nearest in the containment hierarchy) positioned ancestor element. If there is no positioned ancestor element, the nearest ancestor `td`, `th`, `table` will be returned, or the `body` if there are no ancestor table elements either.

**NOTE:**

**`offsetParent` returns `null` in the following situations:**

-   The element or its parent element has the `display` property set to `none`.
-   The element has the `position` property set to `fixed` (firefox returns `<body>`).
-   The element is `<body>` or `<html>`.

`offsetParent` is useful because [`offsetTop`](offsettop) and [`offsetLeft`](offsetleft) are relative to its padding edge.

Syntax
------

    parentObj = element.offsetParent;

-   parentObj is an object reference to the element in which the current element is offset.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-htmlelement-offsetparent">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'offsetParent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`offsetParent`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetParent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/offsetParent</a>
