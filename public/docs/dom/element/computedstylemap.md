# Element.computedStyleMap()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `computedStyleMap()` method of the [`Element`](../element) interface returns a [`StylePropertyMapReadOnly`](../stylepropertymapreadonly) interface which provides a read-only representation of a CSS declaration block that is an alternative to [`CSSStyleDeclaration`](../cssstyledeclaration).

## Syntax

    var stylePropertyMapReadOnly = element.computedStyleMap()

### Parameters

None.

### Return value

A [`StylePropertyMapReadOnly`](../stylepropertymapreadonly) interface.

## Examples

We start with some simple HTML: a paragraph with a link, and a definition list to which we will add all the CSS Property / Value pairs.

    <p>
       <a href="https://example.com">Link</a>
    </p>
    <dl id="regurgitation"></dl>

We add a little bit of CSS

    a {
      --color: red;
      color: var(--color);
    }

We add JavaScript to grab our link and return back a definition list of all the CSS property values using `computedStyleMap().`

    // get the element
    const myElement = document.querySelector('a');

    // get the <dl> we'll be populating
    const stylesList = document.querySelector('#regurgitation');

    // Retrieve all computed styles with computedStyleMap()
    const allComputedStyles = myElement.computedStyleMap();

    // iterate thru the map of all the properties and values, adding a <dt> and <dd> for each
    for (const [prop, val] of allComputedStyles) {
        // properties
        const cssProperty = document.createElement('dt');
        cssProperty.appendChild(document.createTextNode(prop));
        stylesList.appendChild(cssProperty);

        // values
        const cssValue = document.createElement('dd');
        cssValue.appendChild(document.createTextNode(val));
        stylesList.appendChild(cssValue);
    }

In [browsers that support `computedStyleMap()`](#browser_compatibility), you'll see a list of all the CSS properties and values. In other browsers you'll just see a link.

Did you realize how many default CSS properties a link had? Update the '`a`' to the '`p`', and you'll notice a difference in the `margin-top` and `margin-bottom` default computed values.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-element-computedstylemap">CSS Typed OM Level 1<br />
<span class="small">The definition of 'computedStyleMap()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`computedStyleMap`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/computedStyleMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/computedStyleMap</a>
