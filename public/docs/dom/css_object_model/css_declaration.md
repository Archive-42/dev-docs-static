# CSS Declaration

A **CSS declaration** is an abstract concept not exposed as an object in the DOM. It represents a CSS property and value pairing.

A CSS declaration has the following associated properties:

property name  
The property name of the declaration, for example [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color).

value  
The value of the declaration as a list of component values.

important flag  
Either set or unset.

case-sensitive flag  
Set if the property name is defined to be case-sensitive according to the specification, otherwise unset.

## Basic example

The following example shows a CSS rule with a [CSS declaration block](css_declaration_block) for the [&lt;h1&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) element. The CSS declaration block is the lines between the curly braces, it contains two CSS declarations. One for [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style) and another for [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color).

    h1 {
      font-style: italic;
      color: rebeccapurple;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#css-declarations">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSS Declarations' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model/CSS_Declaration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model/CSS_Declaration</a>
