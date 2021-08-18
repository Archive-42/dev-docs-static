# Element.getAttribute()

The `getAttribute()` method of the [`Element`](../element) interface returns the value of a specified attribute on the element. If the given attribute does not exist, the value returned will either be `null` or `""` (the empty string); see [Non-existing attributes](#non-existing_attributes) for details.

## Syntax

    let attribute = element.getAttribute(attributeName);

where

- `attribute` is a string containing the value of `attributeName`.
- `attributeName` is the name of the attribute whose value you want to get.

## Examples

    <!-- example div in an html DOC -->
    <div id="div1">Hi Champ!</div>

    // in a console
    const div1 = document.getElementById('div1');
    //=> <div id="div1">Hi Champ!</div>

    const exampleAttr= div1.getAttribute('id');
    //=> "div1"

    const align = div1.getAttribute('align')
    //=> null

## Description

### Lower casing

When called on an HTML element in a DOM flagged as an HTML document, `getAttribute()` lower-cases its argument before proceeding.

### Non-existing attributes

Essentially all web browsers (Firefox, Internet Explorer, recent versions of Opera, Safari, Konqueror, and iCab, as a non-exhaustive list) return `null` when the specified attribute does not exist on the specified element; this is what [the current DOM specification draft](https://dom.spec.whatwg.org/#dom-element-getattribute) specifies. The old DOM 3 Core specification, on the other hand, says that the correct return value in this case is actually the _empty string_, and some DOM implementations implement this behavior. The implementation of `getAttribute()` in XUL (Gecko) actually follows the DOM 3 Core specification and returns an empty string. Consequently, you should use [`element.hasAttribute()`](hasattribute) to check for an attribute's existence prior to calling `getAttribute()` if it is possible that the requested attribute does not exist on the specified element.

### Retrieving nonce values

For security reasons, [CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) nonces from non-script sources, such as CSS selectors, and `.getAttribute("nonce")` calls are hidden.

    let nonce =  script.getAttribute('nonce');
    // returns empty string

Instead of retrieving the nonce from the content attribute, use the [`nonce`](../htmlorforeignelement/nonce) property:

    let nonce =  script.nonce;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-getattribute">DOM<br />
<span class="small">The definition of 'getAttribute()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getAttribute`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute</a>
