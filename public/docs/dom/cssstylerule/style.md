# CSSStyleRule.style

The read-only `style` property is the [`CSSStyleDeclaration`](../cssstyledeclaration) interface for the [declaration block](https://www.w3.org/TR/1998/REC-CSS2-19980512/syndata.html#block) of the [`CSSStyleRule`](../cssstylerule).

## Syntax

    styleObj = cssRule.style

### Value

A [`CSSStyleDeclaration`](../cssstyledeclaration) object, with the following properties:

computed flag  
Unset.

declarations  
The declared declarations in the rule, in the order they were specified, shorthand properties expanded to longhands.

parent CSS rule  
The context object, which is an alias for [this](https://heycam.github.io/webidl/#this).

owner node  
Null.

## Example

The CSS includes one style rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. `myRules[0].style` therefore returns a [`CSSStyleDeclaration`](../cssstyledeclaration) object representing the declarations defined for `h1`.

    h1 {
      color: pink;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].style); // a CSSStyleDeclaration representing the declarations on the h1.

The declaration block is that part of the style rule that appears within the braces and that actually provides the style definitions (for the selector, the part that comes before the braces).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylerule-style">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleRule: style' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

9

≤12.1

1

4.4

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/style</a>
