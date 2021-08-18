Range.detach()
==============

The `Range.detach()` method does nothing. It used to disable the [`Range`](../range) object and enable the browser to release associated resources. The method has been kept for compatibility.

Syntax
------

    range.detach();

Example
-------

    var range = document.createRange();

    range.selectNode(document.getElementsByTagName("div").item(0));
    range.detach();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-detach">DOM<br />
<span class="small">The definition of 'Range.detach()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-detach">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.detach()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`detach`

1

Starting in Chrome 37, this method is a no-op and has no effect.

12

1-15

Starting in Firefox 15.0, this method is a no-op and has no effect.

9

9

Starting in Opera 24, this method is a no-op and has no effect.

1

Since August 2015 this method is a no-op in [WebKit-based browsers](https://webkit.org/b/148454).

1

Starting in WebView 37, this method is a no-op and has no effect.

18

Starting in Chrome 37, this method is a no-op and has no effect.

4-15

Starting in Firefox 15.0, this method is a no-op and has no effect.

10.1

Starting in Opera 24, this method is a no-op and has no effect.

1

Since August 2015 this method is a no-op in [WebKit-based browsers](https://webkit.org/b/148454).

1.0

Starting in Samsung Internet 3.0, this method is a no-op and has no effect.

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/detach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/detach</a>
