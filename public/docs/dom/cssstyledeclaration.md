# CSSStyleDeclaration

The `CSSStyleDeclaration` interface represents an object that is a CSS declaration block, and exposes style information and various style-related methods and properties.

A `CSSStyleDeclaration` object can be exposed using three different APIs:

- Via [`ElementCSSInlineStyle.style`](elementcssinlinestyle/style), which deals with the inline styles of a single element (e.g., `<div style="...">`).
- Via the [`CSSStyleSheet`](cssstylesheet) API. For example, `document.styleSheets[0].cssRules[0].style` returns a `CSSStyleDeclaration` object on the first CSS rule in the document's first stylesheet.
- Via [`Window.getComputedStyle()`](window/getcomputedstyle), which exposes the `CSSStyleDeclaration` object as a **read-only** interface.

## Attributes

[`CSSStyleDeclaration.cssText`](cssstyledeclaration/csstext)  
Textual representation of the declaration block. Setting this attribute changes the style.

[`CSSStyleDeclaration.length`](cssstyledeclaration/length)<span class="badge inline readonly">Read only </span>  
The number of properties. See the [`item()`](cssstyledeclaration/item) method below.

[`CSSStyleDeclaration.parentRule`](cssstyledeclaration/parentrule)<span class="badge inline readonly">Read only </span>  
The containing [`CSSRule`](cssrule).

### CSS Properties

[`CSSStyleDeclaration.cssFloat`](cssstyledeclaration/cssfloat)  
Special alias for the [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) CSS property.

<span class="page-not-created">`CSSStyleDeclaration` named properties</span>  
Dashed and camel-cased attributes for all supported CSS properties.

## Methods

[`CSSStyleDeclaration.getPropertyPriority()`](cssstyledeclaration/getpropertypriority)  
Returns the optional priority, "important".

[`CSSStyleDeclaration.getPropertyValue()`](cssstyledeclaration/getpropertyvalue)  
Returns the property value given a property name.

[`CSSStyleDeclaration.item()`](cssstyledeclaration/item)  
Returns a CSS property name by its index, or the empty string if the index is out-of-bounds.

An alternative to accessing `nodeList[i]` (which instead returns `undefined` when `i` is out-of-bounds). This is mostly useful for non-JavaScript DOM implementations.

[`CSSStyleDeclaration.removeProperty()`](cssstyledeclaration/removeproperty)  
Removes a property from the CSS declaration block.

[`CSSStyleDeclaration.setProperty()`](cssstyledeclaration/setproperty)  
Modifies an existing CSS property or creates a new CSS property in the declaration block.

[`CSSStyleDeclaration.getPropertyCSSValue()`](cssstyledeclaration/getpropertycssvalue) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
**Only supported via getComputedStyle in Firefox.** Returns the property value as a [`CSSPrimitiveValue`](cssprimitivevalue) or `null` for [shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties).

## Example

    var styleObj = document.styleSheets[0].cssRules[0].style;
    console.log(styleObj.cssText);

    for (var i = styleObj.length; i--;) {
      var nameString = styleObj[i];
      styleObj.removeProperty(nameString);
    }

    console.log(styleObj.cssText);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-cssstyledeclaration-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Merged the <strong>DOM Level 2 Style</strong> <code>CSS2Properties</code> interface into <code>CSSStyleDeclaration</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleDeclaration">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSStyleDeclaration' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSStyleDeclaration`

1

12

1

5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`cssFloat`

1

12

1-17

9

≤12.1

1

4.4

18

4-17

≤12.1

1

1.0

`cssText`

1

12

1

5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`getPropertyCSSValue`

1-40

See [bug 331608](https://crbug.com/331608).

No

See [bug 331608](https://crbug.com/331608).

1-61

Only returns a result if called on the result of `getComputedStyle()`.

No

15-27

See [bug 331608](https://crbug.com/331608).

1

4.4-41

See [bug 331608](https://crbug.com/331608).

18-40

See [bug 331608](https://crbug.com/331608).

4-61

14-27

See [bug 331608](https://crbug.com/331608).

1

1.0-4.0

See [bug 331608](https://crbug.com/331608).

`getPropertyPriority`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`getPropertyValue`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`item`

1

12

1

9

≤12.1

6

4.4

18

4

≤12.1

Yes

1.0

`length`

44

12

1

9

≤12.1

6

4.4

18

4

≤12.1

Yes

1.0

`parentRule`

1

12

1

9

15

1

4.4

18

4

14

1

1.0

`removeProperty`

1

12

1

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`setProperty`

1

12

1

9

9

6

4.4

18

4

10.1

6

1.0

`@@iterator`

51

18

36

No

38

11

51

51

36

41

11

5.0

## See also

- [CSS Properties Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration</a>
