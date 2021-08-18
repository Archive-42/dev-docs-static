HTMLFormControlsCollection
==========================

The `HTMLFormControlsCollection` interface represents a *collection* of HTML *form control elements*. It represents the lists returned by the [`HTMLFormElement`](htmlformelement) interface's [`elements`](htmlformelement/elements) property and the [`HTMLFieldSetElement`](htmlfieldsetelement) interface's <span class="page-not-created">`elements`</span> property.

This interface replaces one method from [`HTMLCollection`](htmlcollection), on which it is based.

Properties
----------

*This interface inherits the properties of its parent, [`HTMLCollection`](htmlcollection).*

Methods
-------

*This interface inherits the methods of its parent, [`HTMLCollection`](htmlcollection).*

[`HTMLFormControlsCollection.namedItem()`](htmlformcontrolscollection/nameditem)  
Returns the [`RadioNodeList`](radionodelist) or the [`Element`](element) in the collection whose `name` or `id` matches the specified name, or `null` if no nodes match. Note that this version of `namedItem()` hide the one inherited from [`HTMLCollection`](htmlcollection). Like that one, in JavaScript, using the array bracket syntax with a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), like `collection["value"]` is equivalent to `collection.namedItem("value")`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/infrastructure.html#htmlformcontrolscollection">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormControlsCollection' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since the last snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/infrastructure.html#htmlformcontrolscollection">HTML5<br />
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

`HTMLFormControlsCollection`

25

79

27

No

15

6.1

≤37

25

27

14

7

1.5

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

-   [`HTMLCollection`](htmlcollection), [`RadioNodeList`](radionodelist), [`HTMLOptionsCollection`](htmloptionscollection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormControlsCollection</a>
