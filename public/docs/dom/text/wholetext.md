Text.wholeText
==============

The `Text.wholeText` read-only property returns the full text of all [`Text`](../text) nodes logically adjacent to the node. The text is concatenated in document order. This allows to specify any text node and obtain all adjacent text as a single string.

Syntax
------

    str = textnode.wholeText;

Notes and example
-----------------

Suppose you have the following simple paragraph within your webpage (with some whitespace added to aid formatting throughout the code samples here), whose DOM node is stored in the variable `para`:

    <p>Thru-hiking is great!  <strong>No insipid election coverage!</strong>
      However, <a href="https://en.wikipedia.org/wiki/Absentee_ballot">casting a
      ballot</a> is tricky.</p>

You decide you don’t like the middle sentence, so you remove it:

    para.removeChild(para.childNodes[1]);

Later, you decide to rephrase things to, “Thru-hiking is great, but casting a ballot is tricky.” *while preserving the hyperlink*. So you try this:

    para.firstChild.data = "Thru-hiking is great, but ";

All set, right? *Wrong!* What happened was you removed the `strong` element, but the removed sentence’s element separated two text nodes. One for the first sentence, and one for the first word of the last. Instead, you now effectively have this:

    <p>Thru-hiking is great, but However, <a
      href="https://en.wikipedia.org/wiki/Absentee_ballot">casting a
      ballot</a> is tricky.</p>

You’d really prefer to treat all those adjacent text nodes as a single one. That’s where `wholeText` comes in: if you have multiple adjacent text nodes, you can access the contents of all of them using `wholeText`. Let’s pretend you never made that last mistake. In that case, we have:

    assert(para.firstChild.wholeText == "Thru-hiking is great!    However, ");

`wholeText` is just a property of text nodes that returns the string of data making up all the adjacent (i.e. not separated by an element boundary) text nodes combined.

Now let’s return to our original problem. What we want is to be able to *replace* the whole text with new text. That’s where [`replaceWholeText()`](replacewholetext) comes in:

    para.firstChild.replaceWholeText("Thru-hiking is great, but ");

We’re removing every adjacent text node (all the ones that constituted the whole text) but the one on which `replaceWholeText()` is called, and we’re changing the remaining one to the new text. What we have now is this:

    <p>Thru-hiking is great, but <a
      href="https://en.wikipedia.org/wiki/Absentee_ballot">casting a
      ballot</a> is tricky.</p>

Some uses of the whole-text functionality may be better served by using `Node.textContent`, or the longstanding [`Element.innerHTML`](../element/innerhtml); that’s fine and probably clearer in most circumstances. If you have to work with mixed content within an element, as seen here, `wholeText` and <span class="internal">`replaceWholeText()`</span> may be useful.

<span class="internal">`replaceWholeText()`</span> [is obsolete](replacewholetext).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-text-wholetext">DOM<br />
<span class="small">The definition of 'Text.wholeText' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Text3-wholeText">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Text.wholeText' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`wholeText`

1

12

3.5

9

Yes

4

Yes

18

4

Yes

3.2

?

See also
--------

-   The [`Text`](../text) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Text/wholeText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Text/wholeText</a>
