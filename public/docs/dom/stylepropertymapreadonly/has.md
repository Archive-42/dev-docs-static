StylePropertyMapReadOnly.has()
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `has()` method of the [`StylePropertyMapReadOnly`](../stylepropertymapreadonly) interface indicates whether the specified property is in the `StylePropertyMapReadOnly` object.

Syntax
------

    var boolean = StylePropertyMapReadOnly.has(property)

### Parameters

property  
The name of a property.

### Return value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

Here we use the `has()` method to see if the padding-top property is present within the button elements style attribute.

    // get the button element
    const buttonEl = document.querySelector('.example');

    // find what's in the style attribute with attributeStyleMap and has()
    const hasPadTop = buttonEl.attributeStyleMap.has('padding-top);

    console.log(hasPadTop); // logs true if padding-top is present in style attribute

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-stylepropertymapreadonly-has">CSS Typed OM Level 1<br />
<span class="small">The definition of 'has()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`has`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/has</a>
