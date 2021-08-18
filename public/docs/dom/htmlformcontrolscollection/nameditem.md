HTMLFormControlsCollection.namedItem()
======================================

The `HTMLFormControlsCollection.namedItem()` method returns the [`RadioNodeList`](../radionodelist) or the [`Element`](../element) in the collection whose `name` or `id` match the specified name, or `null` if no node matches.

Note that this version of `namedItem()` hides the one inherited from [`HTMLCollection`](../htmlcollection). Like that one, in JavaScript, using the array bracket syntax with a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), like `collection["value"]` is equivalent to `collection.namedItem("value")`.

Syntax
------

    var item = collection.namedItem(str);
    var item = collection[str];

### Parameters

-   `str` is a [`DOMString`](../domstring)

### Return value

-   `item` is a [`RadioNodeList`](../radionodelist) , [`Element`](../element), or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null).

Example
-------

### HTML

    <form>
      <input id="my-form-control" type="textarea">
    </form>

### JavaScript

    // Returns the HTMLInputElement representing #my-form-control
    elem1 = document.forms[0]['my-form-control'];

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-htmlformcontrolscollection-nameditem">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormControlsCollection.namedItem()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/infrastructure.html#htmlformcontrolscollection">HTML5<br />
<span class="small">The definition of 'HTMLFormControlsCollection' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>In this snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, the <code>HTMLFormControlsCollections</code> is defined for the first time.</td></tr></tbody></table>

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

`namedItem`

25

79

33

27-33

Returned a [`NodeList`](https://developer.mozilla.org/docs/Web/API/NodeList) instead of a [`RadioNodeList`](https://developer.mozilla.org/docs/Web/API/RadioNodeList).

No

15

6.1

≤37

25

33

27-33

Returned a [`NodeList`](https://developer.mozilla.org/docs/Web/API/NodeList) instead of a [`RadioNodeList`](https://developer.mozilla.org/docs/Web/API/RadioNodeList).

14

7

1.5

See also
--------

-   <span class="page-not-created">`HTMLCollection.namedItem`</span> that it replaces

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection/namedItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection/namedItem</a>
