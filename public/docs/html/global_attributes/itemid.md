itemid
======

The `itemid` [global attribute](../global_attributes) provides microdata in the form of a unique, global identifier of an item. An `itemid` attribute can only be specified for an element that has both [`itemscope`](../global_attributes#attr-itemscope) and [`itemtype`](../global_attributes#attr-itemtype) attributes. Also, `itemid` can only be specified on elements that possess an `itemscope` attribute whose corresponding `itemtype` refers to or defines a vocabulary that supports global identifiers.

The exact meaning of an `itemtype`'s global identifier is provided by the definition of that identifier within the specified vocabulary. The vocabulary defines whether several items with the same global identifier can coexist and, if so, how items with the same identifier are handled.

**Note:** The [WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG) definition specifies that an `itemid` must be a [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL). However, the following example correctly illustrates that a [URN](https://developer.mozilla.org/en-US/docs/Glossary/URN) may also be used. This inconsistency may reflect the incomplete nature of the Microdata specification.

Example
-------

### HTML

    <dl itemscope
        itemtype="http://vocab.example.net/book"
        itemid="urn:isbn:0-330-34032-8">
    <dt>Title <dd itemprop="title">The Reality Dysfunction
    <dt>Author <dd itemprop="author">Peter F. Hamilton
    <dt>Publication date
    <dd><time itemprop="pubdate" datetime="1996-01-26">26 January 1996</time> </dl>

### Structured data

itemscope

itemtype: itemid

http://vocab.example.net/book: urn:isbn:0-330-34032-8

itemprop

title

The Reality Dysfunction

itemprop

author

Peter F. Hamilton

itemprop

pubdate

1996-01-26

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/microdata.html#attr-itemid">HTML Living Standard<br />
<span class="small">The definition of 'itemid' in that specification.</span></a></td></tr></tbody></table>

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

`itemid`

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

-   All [global attributes](../global_attributes).
-   Other, microdata related, global attributes:
    -   [`itemid`](../global_attributes#attr-itemid)
    -   [`itemprop`](../global_attributes#attr-itemprop)
    -   [`itemref`](../global_attributes#attr-itemref)
    -   [`itemscope`](../global_attributes#attr-itemscope)
    -   [`itemtype`](../global_attributes#attr-itemtype)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/itemid</a>
