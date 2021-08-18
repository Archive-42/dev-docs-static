StylePropertyMapReadOnly.entries()
==================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `StylePropertyMapReadOnly.entries()` method returns an array of a given object's own enumerable property `[key, value]` pairs, in the same order as that provided by a [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) loop (the difference being that a for-in loop enumerates properties in the prototype chain as well).

Syntax
------

    StylePropertyMapReadOnly.entries()

### Parameters

None.

### Return value

An array of the given `StylePropertyMapReadOnly` object's own enumerable property `[key, value]` pairs.

Example
-------

Here shows an example of using `StylePropertyMapReadOnly.entries()` method on an elements computed styles.

    // grab a dom element
    const buttonEl = document.querySelector('button');

    // we can retrieve all computed styles with `computedStyleMap`
    const allComputedStyles = buttonEl.computedStyleMap();

    // entries returns an iterable of the items
    const iterableStyles = allComputedStyles.entries();

    // returns a two item array with align-content as the first item and CSSStyleValue as the second
    console.log(iterableStyles.next().value);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#the-stylepropertymap">CSS Typed OM Level 1<br />
<span class="small">The definition of 'entries()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`entries`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/entries</a>
