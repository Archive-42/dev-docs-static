StylePropertyMapReadOnly.get()
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `get()` method of the [`StylePropertyMapReadOnly`](../stylepropertymapreadonly) interface returns a [`CSSStyleValue`](../cssstylevalue) object for the first value of the specified property.

Syntax
------

    var declarationBlock = StylePropertyMapReadOnly.get(property)

### Parameters

property  
The name of the property to retrieve the value of.

### Return value

A [`CSSStyleValue`](../cssstylevalue) object.

Examples
--------

Let's get just a few properties and values. Let's start by creating a link inside a paragraph in our HTML, and adding a definition list which we will populate with JavaScript:

    <p>
       <a href="https://example.com">Link</a>
    </p>
    <dl id="results"></dl>

We add a bit of CSS, including a custom property and an inheritable property:

    p {
      font-weight: bold;
    }
    a {
       --color: red;
       color: var(--color);
    }

We use the Element's `computedStyleMap()` to return a *StylePropertyMapReadOnly* object. We create an array of properties of interest and use the StylePropertyMapReadOnly's `get()` method to get only those values.

    // get the element
    const myElement = document.querySelector('a');

    // Retrieve all computed styles with computedStyleMap()
    const styleMap = myElement.computedStyleMap();

    // get the <dl> we'll be populating
    const stylesList = document.querySelector('#results');

    // array of properties we're interested in
    const ofInterest = ['font-weight', 'border-left-color', 'color', '--color'];

    // iterate over our properties of interest
    for ( let i = 0; i < ofInterest.length; i++ ) {

      // properties
      const cssProperty = document.createElement('dt');
      cssProperty.innerText = ofInterest[i];
      stylesList.appendChild(cssProperty);

      // values
      const cssValue = document.createElement('dd');
      // use get() to find the value
      cssValue.innerText = styleMap.get(ofInterest[i]);
      stylesList.appendChild(cssValue);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-stylepropertymapreadonly-get">CSS Typed OM Level 1<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [CSS Typed Object Model API](../css_typed_om_api)
-   [Learning Houdini: the CSS Typed Object Model](../css_typed_om_api/guide)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StylePropertyMapReadOnly/get</a>
