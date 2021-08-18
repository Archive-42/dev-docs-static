Element.getElementsByTagNameNS()
================================

The `Element.getElementsByTagNameNS()` method returns a live [`HTMLCollection`](../htmlcollection) of elements with the given tag name belonging to the given namespace. It is similar to [`Document.getElementsByTagNameNS`](../document/getelementsbytagnamens), except that its search is restricted to descendants of the specified element.

Syntax
------

    elements = element.getElementsByTagNameNS(namespaceURI, localName)

-   `elements` is a live [`HTMLCollection`](../htmlcollection) of found elements in the order they appear in the tree.
-   `element` is the element from where the search should start. Note that only the descendants of this element are included in the search, not the node itself.
-   `namespaceURI` is the namespace URI of elements to look for (see [`Element.namespaceURI`](namespaceuri) and [`Attr.namespaceURI`](../attr/namespaceuri)). For example, if you need to look for XHTML elements, use the XHTML namespace URI, `http://www.w3.org/1999/xhtml`.
-   `localName` is either the local name of elements to look for or the special value `"*"`, which matches all elements (see [`Element.localName`](localname) and [`Attr.localName`](../attr/localname)).

Example
-------

    // check the alignment on a number of cells in a table in an XHTML document.
    var table = document.getElementById("forecast-table");
    var cells = table.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "td");

    for (var i = 0; i < cells.length; i++) {
        var axis = cells[i].getAttribute("axis");
        if (axis == "year") {
            // grab the data
        }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-getelementsbytagnamens">DOM<br />
<span class="small">The definition of 'Element.getElementsByTagNameNS()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Changed the return value from <a href="../nodelist"><code>NodeList</code></a> to <a href="../htmlcollection"><code>HTMLCollection</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-A6C90942">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Element.getElementsByTagNameNS()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-A6C90942">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Element.getElementsByTagNameNS()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`getElementsByTagNameNS`

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

12

1

\["The behavior of `element.getElementsByTagNameNS` changed between Firefox 3.5 and Firefox 3.6. In Firefox 3.5 and before, this function would automatically case-fold any queries so that a search for \\"foo\\" would match \\"Foo\\" or \\"foo\\". In Firefox 3.6 and later this function is now case-sensitive so that a query for \\"foo\\" will only match \\"foo\\" and not \\"Foo\\". For more background on this, please see the [comment from Henri Sivonen about the change](https://bugzil.la/542185#c5). You can also look at the [relevant part of the standard, which states which parts of the API are case-sensitive and which parts aren't.](https://developer.mozilla.org/docs/Case_Sensitivity_in_class_and_id_Names)", "Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflects the spec change."\]

9

≤12.1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

18

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

4

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflects the spec change.

≤12.1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1.0

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

`all_elements_selector`

1

12

Yes

9

Yes

Yes

1

18

Yes

Yes

Yes

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagNameNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagNameNS</a>
