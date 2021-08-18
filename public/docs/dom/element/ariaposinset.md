Element.ariaPosInSet
====================

The `ariaPosInSet` property of the [`Element`](../element) interface reflects the value of the `aria-posinset` attribute, which defines an element's number or position in the current set of listitems or treeitems.

Syntax
------

    var ariaPosInSet = element.ariaPosInSet;
    element.ariaPosInSet = ariaPosInSet

### Value

A [`DOMString`](../domstring) containing an integer.

Examples
--------

In this example the `aria-posinset` attribute on the element with an ID of `article2` is set to "2". Using `ariaPosInSet` we update the value to "3".

    <article id="article1" aria-posinset="1"> ... </article>
    <article id="article1" aria-posinset="2"> ... </article>

    let el = document.getElementById('article2');
    console.log(el.ariaPosInSet); // "2"
    el.ariaPosInSet = "3"
    console.log(el.ariaPosInSet); // "3"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariaposinset">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaPosInSet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaPosInSet`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPosInSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaPosInSet</a>
