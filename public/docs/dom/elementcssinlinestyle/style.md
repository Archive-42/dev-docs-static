# ElementCSSInlineStyle.style

The `style` read-only property returns the _inline_ style of an element in the form of a [`CSSStyleDeclaration`](../cssstyledeclaration) object that contains a list of all styles properties for that element with values assigned for the attributes that are defined in the element's inline [`style` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style).

See the [CSS Properties Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference) for a list of the CSS properties accessible via `style`. The `style` property has the same (and highest) priority in the CSS cascade as an inline style declaration set via the `style` attribute.

## Syntax

    style = CSSStyleDeclaration.style

## Value

A [`CSSStyleDeclaration`](../cssstyledeclaration) object, with the following properties:

computed flag  
Unset.

parent CSS rule  
Null.

owner node  
`this`

## Setting styles

While this property is considered read-only, it is possible to set an inline style by assigning a string directly to the `style` property. In this case the string is forwarded to [`CSSStyleDeclaration.cssText`](../cssstyledeclaration/csstext). Using `style` in this manner will completely overwrite all inline styles on the element.

Therefore, to add specific styles to an element without altering other style values, it is generally preferable to set individual properties on the [`CSSStyleDeclaration`](../cssstyledeclaration) object. For example, `element.style.backgroundColor = "red"`.

A style declaration is reset by setting it to `null` or an empty string, e.g., `elt.style.color = null`. Internet Explorer requires setting it to an empty string, and does not do anything when setting it to `null`.

### Getting style information

The `style` property is not useful for completely learning about the styles applied on the element, since it represents only the CSS declarations set in the element's inline `style` attribute, not those that come from style rules elsewhere, such as style rules in the [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) section, or external style sheets. To get the values of all CSS properties for an element you should use [`Window.getComputedStyle()`](../window/getcomputedstyle) instead.

The following code snippet demonstrates the difference between the values obtained using the element's `style` property and that obtained using the `getComputedStyle()` method:

    <!DOCTYPE HTML>
    <html>
      <body style="font-weight:bold;">
        <div style="color:red" id="myElement">..</div>
      </body>
    </html>

    var element = document.getElementById("myElement");
    var out = "";
    var elementStyle = element.style;
    var computedStyle = window.getComputedStyle(element, null);

    for (prop in elementStyle) {
      if (elementStyle.hasOwnProperty(prop)) {
        out += "  " + prop + " = '" + elementStyle[prop] + "' > '" + computedStyle[prop] + "'\n";
      }
    }
    console.log(out)

The output would be something like:

    ...
    fontWeight = '' > 'bold'
    color = 'red' > 'rgb(255, 0, 0)'
    ...

Note the presence of the value `bold` for `font-weight` in the computed style and the absence of it in the element's `style` property

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-elementcssinlinestyle-style">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'the <code>ElementCSSInlineStyle.style</code> property' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`style`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

## See also

- [Using dynamic styling information](../css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style</a>
