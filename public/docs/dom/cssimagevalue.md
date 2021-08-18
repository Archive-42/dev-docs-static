# CSSImageValue

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSImageValue` interface of the [CSS Typed Object Model API](css_object_model#css_typed_object_model) represents values for properties that take an image, for example [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image), [`list-style-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image), or [`border-image-source`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source). The CSSImageValue object represents an `<image>` that involves an URL, such as `url()` or `image()`, but not `linear-gradient() `or `element()` .

## Properties

None.

## Methods

_Inherits methods from [`CSSStyleValue`](cssstylevalue)._

## Examples

We create an element

    <button>Magic Wand</button>

We add some CSS, including a background image requesting a binary file:

    button {
      display: inline-block;
      min-height: 100px; min-width: 100px;
      background: no-repeat 5% center url(https://mdn.mozillademos.org/files/16793/magicwand.png) aqua;
    }

We get the element's style map. We then get() the background-image from the stylemap and stringify it:

    // get the element
    const button = document.querySelector( 'button' );

    // Retrieve all computed styles with computedStyleMap()
    const allComputedStyles = button.computedStyleMap();

    // Return the CSSImageValue Example
    console.log( allComputedStyles.get('background-image') );
    console.log( allComputedStyles.get('background-image').toString() );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#imagevalue-objects">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSImageValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSImageValue`

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

## See also

- [`CSSKeywordValue`](csskeywordvalue)
- [`CSSNumericValue`](cssnumericvalue)
- [`CSSPositionValue`](csspositionvalue)
- [`CSSTransformValue`](csstransformvalue)
- [`CSSUnparsedValue`](cssunparsedvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSImageValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSImageValue</a>
