# CSSPageRule.style

The `style` read-only property of the [`CSSPageRule`](../csspagerule) interface returns a [`CSSStyleDeclaration`](../cssstyledeclaration) object. This represents an object that is a [CSS declaration block](../css_object_model/css_declaration_block), and exposes style information and various style-related methods and properties.

## Syntax

    var style = CSSPageRule.style;

### Value

A [`CSSStyleDeclaration`](../cssstyledeclaration) object, which represents a [CSS declaration block](../css_object_model/css_declaration_block) with the following properties:

computed flag  
Unset.

declarations  
The declared declarations in the rule, in the order they were specified, shorthand properties expanded to longhands.

parent CSS rule  
The context object, which is an alias for [this](https://heycam.github.io/webidl/#this).

owner node  
Null.

## Examples

The stylesheet includes a [`@page`](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) rule. Getting a list of rules, then returning the value of the style property will return a [`CSSStyleDeclaration`](../cssstyledeclaration) object.

    @page {
      margin: 1cm;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].style); // returns a CSSStyleDeclaration object

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstylerule-style">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSPageRule.style' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSPageRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSPageRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

12

9

≤12.1

3

1

18

14

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule/style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPageRule/style</a>
