itemref
=======

Properties that are not descendants of an element with the [`itemscope`](../global_attributes#attr-itemscope) attribute can be associated with an item using the [global attribute](../global_attributes) `itemref`.

`itemref` provides a list of element IDs (not `itemid`s) elsewhere in the document, with additional properties

The `itemref` attribute can only be specified on elements that have an `itemscope` attribute specified.

**Note:** the `itemref` attribute is not part of the microdata data model. It is merely a syntactic construct to aid authors in adding annotations to pages where the data to be annotated does not follow a convenient tree structure. For example, it allows authors to mark up data in a table so that each column defines a separate item while keeping the properties in the cells.

Example
-------

### HTML

    <div itemscope id="amanda" itemref="a b"></div>
    <p id="a">Name: <span itemprop="name">Amanda</span> </p>
    <div id="b" itemprop="band" itemscope itemref="c"></div>
    <div id="c">
        <p>Band: <span itemprop="name">Jazz Band</span> </p>
        <p>Size: <span itemprop="size">12</span> players</p>
    </div>

### Structured data

<span class="small">(in [JSON-LD](https://json-ld.org/) format)</span>

    {
      "@id": "amanda",
      "name": "Amanda",
      "band": {
        "@id": "b",
        "name": "Jazz Band",
        "size": 12
      }
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/microdata.html#attr-itemref">HTML Living Standard<br />
<span class="small">The definition of 'itemref' in that specification.</span></a></td></tr></tbody></table>

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

`itemref`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [Other different global attributes](../global_attributes)
-   Other, microdata related, global attributes:
    -   [`itemid`](../global_attributes#attr-itemid)
    -   [`itemprop`](../global_attributes#attr-itemprop)
    -   [`itemref`](../global_attributes#attr-itemref)
    -   [`itemscope`](../global_attributes#attr-itemscope)
    -   [`itemtype`](../global_attributes#attr-itemtype)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemref" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemref</a>
