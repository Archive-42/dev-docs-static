HTMLAreaElement.rel
===================

The `HTMLAreaElement.rel` property reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-rel) attribute. It is a [`DOMString`](../domstring) containing a space-separated list of [link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) indicating the relationship between the resource represented by the [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) element and the current document.

Syntax
------

    var relstr = areaElt.rel;
    areaElt.rel = relstr;

Example
-------

    var areas = document.getElementsByTagName("area");
    var length = areas.length;
    for (var i = 0; i < length; i++) {
      alert("Rel: " + areas[i].rel);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-area-rel">HTML Living Standard<br />
<span class="small">The definition of 'rel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

54

12

30

11

41

9

54

54

30

41

9

6.0

See also
--------

-   The equivalent property on [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link), [`HTMLAnchorElement.rel`](../htmlanchorelement/rel) and [`HTMLLinkElement.rel`](../htmllinkelement/rel).
-   The very same list but as tokens: [`HTMLAreaElement.relList`](rellist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/rel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/rel</a>
