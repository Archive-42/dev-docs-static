Range.toString()
================

The `Range.toString()` method is a stringifier returning the text of the [`Range`](../range).

Alerting the contents of a [`Range`](../range) makes an implicit `toString()` call, so comparing range and text through an alert dialog is ineffective.

Syntax
------

    text = range.toString();

Example
-------

### HTML

    <p>This example logs <b>everything</b> between the bold <b>words</b>. Look at the output below.</p>
    <p id="log"></p>

### JavaScript

    const range = document.createRange();

    range.setStartBefore(document.getElementsByTagName('b').item(0), 0);
    range.setEndAfter(document.getElementsByTagName('b').item(1), 0);
    document.getElementById('log').textContent = range.toString();

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-stringifier">DOM<br />
<span class="small">The definition of 'Range.toString()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-toString">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.toString()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`toString`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/toString</a>
