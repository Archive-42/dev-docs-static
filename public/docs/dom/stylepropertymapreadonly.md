StylePropertyMapReadOnly
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `StylePropertyMapReadOnly` interface of the [CSS Typed Object Model API](css_object_model#CSS_Typed_Object_Model) provides a read-only representation of a CSS declaration block that is an alternative to [`CSSStyleDeclaration`](cssstyledeclaration). Retrieve an instance of this interface using [`Element.computedStyleMap()`](element/computedstylemap).

Properties
----------

[`StylePropertyMapReadOnly.size`](stylepropertymapreadonly/size)  
Returns an unsinged long integer containing the size of the `StylePropertyMapReadOnly` object.

Methods
-------

[`StylePropertyMapReadOnly.entries()`](stylepropertymapreadonly/entries)  
Returns an array of a given object's own enumerable property `[key, value]` pairs, in the same order as that provided by a [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) loop (the difference being that a for-in loop enumerates properties in the prototype chain as well).

[`StylePropertyMapReadOnly.forEach()`](stylepropertymapreadonly/foreach)  
Executes a provided function once for each element of `StylePropertyMapReadOnly`.

[`StylePropertyMapReadOnly.get()`](stylepropertymapreadonly/get)  
Returns the value of the specified property.

[`StylePropertyMapReadOnly.getAll()`](stylepropertymapreadonly/getall)  
Returns an array of [`CSSStyleValue`](cssstylevalue) objects containing the values for the provided property.

[`StylePropertyMapReadOnly.has()`](stylepropertymapreadonly/has)  
Indicates whether the specified property is in the `StylePropertyMapReadOnly` object.

[`StylePropertyMapReadOnly.keys()`](stylepropertymapreadonly/keys)  
Returns a new Array Iterator containing the keys for each item in `StylePropertyMapReadOnly`.

[`StylePropertyMapReadOnly.values()`](stylepropertymapreadonly/values)  
Returns a new Array Iterator containing the values for each index in the `StylePropertyMapReadOnly` object.

Examples
--------

We have to have an element to observe:

    <p>
       This is a paragraph with some text. We can add some CSS, or not. The
       style map will include all the default and inherted CSS property values.
    </p>
    <dl id="output"></dl>

We add a touch of CSS with a custom property to better demonstrate the output:

    p {
       --someVariable: 1.6em;
       --someOtherVariable: translateX(33vw);
       --anotherVariable: 42;
       line-height: var(--someVariable);
    }

We add JavaScript to grab our paragraph and return back a definition list of all the default CSS property values using [`Element.computedStyleMap()`](element/computedstylemap).

    // get the element
    const myElement = document.querySelector('p');

    // get the <dl> we'll be populating
    const stylesList = document.querySelector('#output');

    // Retrieve all computed styles with computedStyleMap()
    const stylePropertyMap = myElement.computedStyleMap();

    // iterate thru the map of all the properties and values, adding a <dt> and <dd> for each
    for (const [prop, val] of stylePropertyMap) {
        // properties
        const cssProperty = document.createElement('dt');
        cssProperty.innerText = prop;
        stylesList.appendChild(cssProperty);

        // values
        const cssValue = document.createElement('dd');
        cssValue.innerText = val;
        stylesList.appendChild(cssValue);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#stylepropertymapreadonly">CSS Typed OM Level 1<br />
<span class="small">The definition of 'StylePropertyMapReadOnly' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`StylePropertyMapReadOnly`

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

`get`

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

`values`

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

`@@iterator`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly</a>
