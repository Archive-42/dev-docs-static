HTMLLinkElement.rel
===================

The `HTMLLinkElement.rel` property reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-rel) attribute. It is a [`DOMString`](../domstring) containing a space-separated list of [link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) indicating the relationship between the resource represented by the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element and the current document.

The most common use of this attribute is to specify a link to an external style sheet: the property is set to `stylesheet`, and the [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-href) attribute is set to the URL of an external style sheet to format the page.

Syntax
------

    var relstr = linkElt.rel;
    linkElt.rel = relstr;

Example
-------

    var links = document.getElementsByTagName('link');
    var length = links.length;
    for (var i = 0; i < length; i++) {
      alert(links[i]);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#attr-link-rel">HTML Living Standard<br />
<span class="small">The definition of 'rel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-41369587">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'rel' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-41369587">Document Object Model (DOM) Level 1 Specification<br />
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

-   The equivalent property on [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area), [`HTMLAnchorElement.rel`](../htmlanchorelement/rel) and [`HTMLAreaElement.rel`](../htmlareaelement/rel).
-   The very same list but as tokens: [`HTMLLinkElement.relList`](rellist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/rel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/rel</a>
