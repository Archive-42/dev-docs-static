StylePropertyMapReadOnly.keys()
===============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `StylePropertyMapReadOnly.keys()` method returns a new Array Iterator containing the keys for each item in `StylePropertyMapReadOnly`

Syntax
------

    StylePropertyMapReadOnly.keys()

### Parameters

None.

### Return value

A new [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

Example
-------

In this example we use the `keys()` method to be able to access the properties within our [`Element.computedStyleMap()`](../element/computedstylemap).

    // get a button element
    const buttonEl = document.querySelector('button');

    // we can retrieve all computed styles with `computedStyleMap`
    const allComputedStyles = buttonEl.computedStyleMap();

    // keys returns an iterable list of properties
    const props = allComputedStyles.keys();
    console.log(props.next().value); // returns align-content

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#the-stylepropertymap">CSS Typed OM Level 1<br />
<span class="small">The definition of 'keys()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`keys`

66

79

No

No

53

No

66

66

No

47

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/keys</a>
