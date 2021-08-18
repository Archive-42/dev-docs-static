DOMTokenList.values()
=====================

The `values()` method of the [`DOMTokenList`](../domtokenlist) interface returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing developers to go through all values contained in the `DOMTokenList`. The individual values are [`DOMString`](../domstring) objects.

Syntax
------

    tokenList.values();

### Parameters

None.

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

Examples
--------

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We when retrieve an iterator containing the values using `values()`, then iterate through those values using a [for ... of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) loop, writing each one to the `<span>`'s [`Node.textContent`](../node/textcontent).

First, the HTML:

    <span class="a b c"></span>

Now the JavaScript:

    var span = document.querySelector("span");
    var classes = span.classList;
    var iterator = classes.values();

    for(var value of iterator) {
      span.textContent += value + ' ++ ';
    }

The output looks like this:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#domtokenlist">DOM<br />
<span class="small">The definition of 'values() (as iterable&lt;Node&gt;)' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`values`

42

16

50

No

32

10.1

45

45

50

32

10.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/values</a>
