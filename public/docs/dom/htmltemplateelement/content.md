HTMLTemplateElement.content
===========================

The `HTMLTemplateElement.content` property returns a `<template>` element's template contents (a [`DocumentFragment`](../documentfragment)).

Syntax
------

    var documentFragment = templateElement.content

Example
-------

    var templateElement = document.querySelector("#foo");
    var documentFragment = templateElement.content.cloneNode(true);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-template-content">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTemplateElement interface' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/scripting-1.html#dom-template-content">HTML5<br />
<span class="small">The definition of 'HTMLTemplateElement interface' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`content`

26

13

22

No

15

6.1

≤37

26

22

Yes

6.1

1.5

See also
--------

-   [`HTMLTemplateElement`](../htmltemplateelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement/content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement/content</a>
