StylePropertyMapReadOnly.size
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `size` read-only property of the [`StylePropertyMapReadOnly`](../stylepropertymapreadonly) interface returns an unsinged long integer containing the size of the `StylePropertyMapReadOnly` object.

Syntax
------

    var size = StylePropertyMapReadOnly.size

### Value

An unsigned long integer.

Example
-------

Here we use the size property to return the total entries within the button elements [`computedStyleMap`](../element/computedstylemap).

    // grab our element
    const buttonEl = document.querySelector('button');

    // we can retrieve all computed styles with `computedStyleMap`
    const allComputedStyles = buttonEl.computedStyleMap();

    // use size to get the total styles within the map
    const amountStyles = allComputedStyles.size;
    console.log(amountStyles); // logs 338

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-stylepropertymapreadonly-size">CSS Typed OM Level 1<br />
<span class="small">The definition of 'size' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`size`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/size</a>