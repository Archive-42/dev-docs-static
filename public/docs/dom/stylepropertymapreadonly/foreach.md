StylePropertyMapReadOnly.forEach()
==================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `StylePropertyMapReadOnly.forEach()` method executes a provided function once for each element of [`StylePropertyMapReadOnly`](../stylepropertymapreadonly).

Syntax
------

    StylePropertyMapReadOnly.forEach(function callback(currentValue[, index[, array]]) {
        //your code
    }[, thisArg]);

### Parameters

`callback`  
The function to execute for each element, taking three arguments:

`currentValue`  
The value of the current element being processed.

 `index`<span class="badge inline optional">Optional</span>   
The index of the current element being processed.

 `array`<span class="badge inline optional">Optional</span>   
The StylePropertyMapReadOnly that`forEach()` is being called on.

 `thisArg` <span class="badge inline optional">Optional</span>   
Value to use as `this` (i.e the reference `Object`) when executing `callback`.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

Example
-------

Here is an example of using `forEach()` on a retrieved [`Element.computedStyleMap()`](../element/computedstylemap).

    // get a button element
    const buttonEl = document.querySelector('.example');

    // we can retrieve all computed styles with `computedStyleMap`
    const allComputedStyles = buttonEl.computedStyleMap();

    // forEach will allow us to run code over each prop/val pair
    allComputedStyles.forEach((elem, index, arr) => {
      // oode to run for each pair
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#the-stylepropertymap">CSS Typed OM Level 1<br />
<span class="small">The definition of 'forEach()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`forEach`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/forEach</a>
