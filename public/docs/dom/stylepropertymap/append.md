StylePropertyMap.append()
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `append()` method of the [`StylePropertyMap`](../stylepropertymap) interface adds the passed CSS value to the `StylePropertyMap` with the given property.

Syntax
------

    StylePropertyMap.append(property,value)

### Parameters

property  
An identifier indicating the stylistic feature (e.g. font, width, background color) to add.

value  
The value the given property should have.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

Example
-------

This example shows an extra background image value being added to the [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image) property of the element, using <span class="page-not-created">`Element.attributeStyleMap`</span>.

    // get the button element
    const buttonEl = document.querySelector('button');

    // append another value to the background-image property set on the attribute
    buttonEl.attributeStyleMap.append('background-image', 'linear-gradient(180deg, blue, black');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-stylepropertymap-append">CSS Typed OM Level 1<br />
<span class="small">The definition of 'append()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`append`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMap/append" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMap/append</a>
