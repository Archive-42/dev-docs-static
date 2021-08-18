Range.createContextualFragment()
================================

The `Range.createContextualFragment()` method returns a [`DocumentFragment`](../documentfragment) by invoking the HTML fragment parsing algorithm or the XML fragment parsing algorithm with the start of the range (the *parent* of the selected node) as the context node. The HTML fragment parsing algorithm is used if the range belongs to a `Document` whose HTMLness bit is set. In the HTML case, if the context node would be `html`, for historical reasons the fragment parsing algorithm is invoked with `body` as the context instead.

Syntax
------

    documentFragment = range.createContextualFragment(tagString)

### Parameters

`tagString`  
Text that contains text and tags to be converted to a document fragment.

Example
-------

    var tagString = "<div>I am a div node</div>";
    var range = document.createRange();

    // Make the parent of the first div in the document become the context node
    range.selectNode(document.getElementsByTagName("div").item(0));
    var documentFragment = range.createContextualFragment(tagString);
    document.body.appendChild(documentFragment);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#dom-range-createcontextualfragment">DOM Parsing and Serialization<br />
<span class="small">The definition of 'Range.createContextualFragment()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`createContextualFragment`

1

12

1

11

≤12.1

9

1

18

4

≤12.1

Yes

1.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/createContextualFragment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/createContextualFragment</a>
