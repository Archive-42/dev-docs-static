# CSS Declaration Block

A **CSS declaration block** is an ordered collection of CSS properties and values. It is represented in the DOM as a [`CSSStyleDeclaration`](../cssstyledeclaration).

Each property and value pairing is known as a [CSS declaration](css_declaration). The CSS declaration block has the following associated properties:

computed flag  
Set if the [`CSSStyleDeclaration`](../cssstyledeclaration) object is a computed rather than specified style. Unset by default.

declarations  
The [CSS declarations](css_declaration) associated with this object.

parent CSS rule  
The [`CSSRule`](../cssrule) that the CSS declaration block is associated with, otherwise null.

owner node  
The [`element`](../element) that the CSS declaration block is associated with, otherwise null.

updating flag  
Set when the CSS declaration block is updating the owner node's [`style`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-style) attribute.

When a [`CSSStyleDeclaration`](../cssstyledeclaration) is returned by a [CSS Object Model (CSSOM)](../css_object_model) interface these properties are set to appropriate values as defined by the specification.

## Basic example

The following example shows a CSS rule with a declaration block for the [&lt;h1&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) element. The CSS declaration block is the lines between the curly braces.

    h1 {
      margin: 0 auto;
      font-family: "Helvetica Neue", "Arial", sans-serif;
      font-style: italic;
      color: rebeccapurple;
    }

We can return a [`CSSStyleDeclaration`](../cssstyledeclaration) representing this CSS declaration block using [`CSSStyleRule.style`](../cssstylerule/style).

    let myRules = document.styleSheets[0].cssRules;
    let rule = myRules[0]; // a CSSStyleRule
    console.log(rule.style); // a CSSStyleDeclaration object

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#css-declaration-blocks">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSS Declaration Blocks' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model/CSS_Declaration_Block" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model/CSS_Declaration_Block</a>
