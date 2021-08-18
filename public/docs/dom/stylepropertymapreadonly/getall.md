StylePropertyMapReadOnly.getAll()
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getAll()` method of the [`StylePropertyMapReadOnly`](../stylepropertymapreadonly) interface returns an array of [`CSSStyleValue`](../cssstylevalue) objects containing the values for the provided property.

Syntax
------

    var cssStyleValues[] = StylePropertyMapReadOnly.getAll(property)

### Parameters

property  
The name of the property to retrieve all values of.

### Return value

An array of [`CSSStyleValue`](../cssstylevalue) objects.

Example
-------

The following example uses `getAll()` with the [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image) property. An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) is returned which contains an item for each background image declared.

    // get a button element
    const buttonEl = document.querySelector('button');

    // we can retrieve all computed styles with `computedStyleMap`
    const allComputedStyles = buttonEl.computedStyleMap();

    // use getAll() with the background image property
    const allBkImages = allComputedStyles.getAll('background-image');
    console.log(allBkImages); // logs an array with each background image as an item

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-stylepropertymapreadonly-getall">CSS Typed OM Level 1<br />
<span class="small">The definition of 'getAll()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAll`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/getAll</a>
