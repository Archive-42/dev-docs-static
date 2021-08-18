StylePropertyMap.delete()
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `delete()` method of the [`StylePropertyMap`](../stylepropertymap) interface removes the CSS declaration with the given property.

Syntax
------

    StylePropertyMap.delete(property)

### Parameters

property  
An identifier indicating the stylistic feature (e.g. font, width, background color) to remove.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

Example
-------

The following example removes the [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image) property from the element's [style attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style).

    // get the button element
    const buttonEl = document.querySelector('button');

    // remove background-image from style attribute
    buttonEl.attributeStyleMap.delete('background-image');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-stylepropertymap-delete">CSS Typed OM Level 1<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`delete`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMap/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMap/delete</a>
