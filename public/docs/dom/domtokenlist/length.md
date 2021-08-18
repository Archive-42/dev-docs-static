DOMTokenList.length
===================

The `length` read-only property of the [`DOMTokenList`](../domtokenlist) interface is an `integer` representing the number of objects stored in the object.

Syntax
------

    tokenList.length;

### Value

An `integer`.

Examples
--------

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist), then write the length of the list to the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b c"></span>

Now the JavaScript:

    let span = document.querySelector("span");
    let classes = span.classList;
    let length = classes.length;

    span.textContent = `classList length = ${length}`;

The output looks like this:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domtokenlist-length">DOM<br />
<span class="small">The definition of 'length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`length`

8

12

50

10

Yes

5.1

3

18

50

Yes

5.1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/length</a>
