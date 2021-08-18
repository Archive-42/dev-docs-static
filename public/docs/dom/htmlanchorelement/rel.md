HTMLAnchorElement.rel
=====================

The `HTMLAnchorElement.rel` property reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-rel) attribute. It is a [`DOMString`](../domstring) containing a space-separated list of [link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) indicating the relationship between the resource represented by the [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element and the current document.

Syntax
------

    var relstr = anchorElt.rel;
    anchorElt.rel = relstr;

Example
-------

    var anchors = document.getElementsByTagName("a");
    var length = anchors.length;
    for (var i = 0; i < length; i++) {
      alert("Rel: " + anchors[i].rel);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#dom-a-rel">HTML Living Standard<br />
<span class="small">The definition of 'rel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-3815891">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'rel' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-3815891">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'rel' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`rel`

1

12

1

5.5

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

-   The equivalent property on [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) and [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link), [`HTMLAreaElement.rel`](../htmlareaelement/rel) and [`HTMLLinkElement.rel`](../htmllinkelement/rel).
-   The very same list but as tokens: [`HTMLAnchorElement.relList`](rellist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/rel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/rel</a>
