StylePropertyMap.clear()
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `clear()` method of the [`StylePropertyMap`](../stylepropertymap) interface removes all declarations in the `StylePropertyMap`.

Syntax
------

    StylePropertMap.clear()

### Parameters

None.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

Example
-------

The following example removes all styles within the elements [style attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style).

    // get the button element
    const buttonEl = document.querySelector('.example');

    // remove all styles from the style attribute
    buttonEl.attributeStyleMap.clear();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-stylepropertymap-clear">CSS Typed OM Level 1<br />
<span class="small">The definition of 'clear()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clear`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMap/clear" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMap/clear</a>
