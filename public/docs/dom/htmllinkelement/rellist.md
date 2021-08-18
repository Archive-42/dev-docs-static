HTMLLinkElement.relList
=======================

The `HTMLLinkElement.relList` read-only property reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-rel) attribute. It is a live [`DOMTokenList`](../domtokenlist) containing the set of [link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) indicating the relationship between the resource represented by the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element and the current document.

The property itself is read-only, meaning you can substitute the [`DOMTokenList`](../domtokenlist) by another one, but the content of the returned list can be changed.

Syntax
------

    var relstr = linkElt.relList;

Example
-------

    var links = document.getElementsByTagName("link");
    var length = links.length;
    for (var i = 0; i < length; i++) {
      var list = links[i].relList;
      var listLength = list.length;
      console.log("New link found.");
      for (var j = 0; j < listLength; j++) {
        console.log(list[j]);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#dom-link-rellist">HTML Living Standard<br />
<span class="small">The definition of 'relList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`relList`

50

17

30

No

37

9

50

50

30

37

9

5.0

See also
--------

-   The equivalent property on [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area), [`HTMLAnchorElement.relList`](../htmlanchorelement/rellist) and [`HTMLAreaElement.relList`](../htmlareaelement/rellist).
-   The very same list but as a space-separated tokens in a [`DOMString`](../domstring): [`HTMLLinkElement.rel`](rel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/relList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/relList</a>
