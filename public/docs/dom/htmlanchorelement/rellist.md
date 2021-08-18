HTMLAnchorElement.relList
=========================

The `HTMLAnchorElement.relList` read-only property reflects the [`rel`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-rel) attribute. It is a live [`DOMTokenList`](../domtokenlist) containing the set of [link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) indicating the relationship between the resource represented by the [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element and the current document.

The property itself is read-only, meaning you can't substitute the [`DOMTokenList`](../domtokenlist) with another one, but its contents can still be changed.

Syntax
------

    var relstr = anchorElt.relList;

Example
-------

    var anchors = document.getElementsByTagName("a");
    var length = anchors.length;
    for (var i = 0; i < length; i++) {
      var list = anchors[i].relList;
      var listLength = list.length;
      console.log("New anchor node found with", listLength, "link types in relList.");
      for (var j = 0; j < listLength; j++) {
        console.log(list[j]);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-a-rellist">HTML Living Standard<br />
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

65

18

30

No

52

9

65

65

30

47

9

9.0

See also
--------

-   The equivalent property on [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) and [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link), [`HTMLAreaElement.relList`](../htmlareaelement/rellist) and [`HTMLLinkElement.relList`](../htmllinkelement/rellist).
-   The very same list but as a space-separated tokens in a [`DOMString`](../domstring): [`HTMLAnchorElement.rel`](rel)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/relList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/relList</a>
