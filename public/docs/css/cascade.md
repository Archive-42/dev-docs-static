# Introducing the CSS Cascade

The **cascade** is an algorithm that defines how to combine property values originating from different sources. It lies at the core of CSS, as emphasized by the name: _Cascading_ Style Sheets. This article explains what the cascade is, the order in which [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) [declarations](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration) cascade, and how this affects you, the web developer.

## Which CSS entities participate in the cascade

Only CSS declarations, that is property/value pairs, participate in the cascade. This means that [at-rules](at-rule) containing entities other than declarations, such as a [`@font-face`](@font-face) rule containing _descriptors_, don't participate in the cascade. In these cases, only the at-rule as a whole participates in the cascade: here, the `@font-face` identified by its `font-family` descriptor. If several `@font-face` rules with the same descriptor are defined, only the most appropriate `@font-face`, as a whole, is considered.

While the declarations contained in most at-rules — such as those in [`@media`](@media), [`@document`](@document), or [`@supports`](@supports) — participate in the cascade, declarations contained in [`@keyframes`](@keyframes) don't. As with `@font-face`, only the at-rule as a whole is selected via the cascade algorithm.

Finally, note that [`@import`](@import) and [`@charset`](@charset) obey specific algorithms and aren't affected by the cascade algorithm.

## Origin of CSS declarations

The CSS cascade algorithm's job is to select CSS declarations in order to determine the correct values for CSS properties. CSS declarations originate from different origins: the **[User-agent stylesheets](#user-agent_stylesheets)**, the **[Author stylesheets](#author_stylesheets)**, and the **[User stylesheets](#user_stylesheets)**.

Though style sheets come from these different origins, they overlap in scope; to make this work, the cascade algorithm defines how they interact.

### User-agent stylesheets

The browser has a basic style sheet that gives a default style to any document. These style sheets are named **user-agent stylesheets**. Some browsers use actual style sheets for this purpose, while others simulate them in code, but the end result is the same.

Some browsers let users modify the user-agent stylesheet. Although some constraints on user-agent stylesheets are set by the HTML specification, browsers still have a lot of latitude: that means that significant differences exist from one browser to another. To simplify the development process, Web developers often use a CSS reset style sheet, forcing common properties values to a known state before beginning to make alterations to suit their specific needs.

### Author stylesheets

**Author stylesheets** are the most common type of style sheet. These are style sheets that define styles as part of the design of a given web page or site. The author of the page defines the styles for the document using one or more stylesheets, which define the look and feel of the website — its theme.

### User stylesheets

The user (or reader) of the web site can choose to override styles in many browsers using a custom **user stylesheet** designed to tailor the experience to the user's wishes.

## Cascading order

The cascading algorithm determines how to find the value to apply for each property for each document element.

1.  It first filters all the rules from the different sources to keep only the rules that apply to a given element. That means rules whose selector matches the given element and which are part of an appropriate `media` at-rule.
2.  Then it sorts these rules according to their importance, that is, whether or not they are followed by `!important`, and by their origin. The cascade is in ascending order, which means that `!important` values from a user-defined style sheet have precedence over normal values originated from a user-agent style sheet:
    <table><thead><tr class="header"><th></th><th>Origin</th><th>Importance</th></tr></thead><tbody><tr class="odd"><td>1</td><td>user agent</td><td>normal</td></tr><tr class="even"><td>2</td><td>user</td><td>normal</td></tr><tr class="odd"><td>3</td><td>author</td><td>normal</td></tr><tr class="even"><td>4</td><td>animations</td><td></td></tr><tr class="odd"><td>5</td><td>author</td><td><code>!important</code></td></tr><tr class="even"><td>6</td><td>user</td><td><code>!important</code></td></tr><tr class="odd"><td>7</td><td>user agent</td><td><code>!important</code></td></tr><tr class="even"><td>8</td><td>transitions</td><td></td></tr></tbody></table>

3.  In case of equality, the [specificity](specificity) of a value is considered to choose one or the other.

## Resetting styles

After your content has finished altering styles, it may find itself in a situation where it needs to restore them to a known state. This may happen in cases of animations, theme changes, and so forth. The CSS property [`all`](all) lets you quickly set (almost) everything in CSS back to a known state.

`all` lets you opt to immediately restore all properties to any of their initial (default) state, the state inherited from the previous level of the cascade, a specific origin (the user-agent stylesheet, the author stylesheet, or the user stylesheet), or even to clear the values of the properties entirely.

## CSS animations and the cascade

[CSS animations](css_animations), using [`@keyframes`](@keyframes) at-rules, define animations between states. Keyframes don't cascade, meaning that at any given time CSS takes values from only one single [`@keyframes`](@keyframes), and never mixes multiple ones together.

When several keyframes are appropriate, it chooses the latest defined in the most important document, but never combined all together.

## Example

Let's look at an example involving multiple sources of CSS across the various origins; here we have a user agent style sheet, two author style sheets, a user stylesheet, and inline styles within the HTML:

**User-agent CSS:**

    li { margin-left: 10px }

**Author CSS 1:**

    li { margin-left: 0 } /* This is a reset */

**Author CSS 2:**

    @media screen {
      li { margin-left: 3px }
    }

    @media print {
      li { margin-left: 1px }
    }

**User CSS:**

    .specific { margin-left: 1em }

**HTML:**

    <ul>
      <li class="specific">1<sup>st</sup></li>
      <li>2<sup>nd</sup></li>
    </ul>

In this case, declarations inside `li` and `.specific` rules should apply. No declaration is marked as `!important`, so the precedence order is author style sheets before user style sheets or user-agent stylesheet.

So three declarations are in competition:

    margin-left: 0

    margin-left: 3px

    margin-left: 1px

The last one is ignored (on a screen), and the first two have the same selector, hence the same specificity. Therefore, it is the last one that is then selected:

    margin-left: 3px

Note that the declaration defined in the user CSS, though having a greater specificity, is not chosen as the cascade algorithm is applied before the specificity algorithm.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-cascade/">CSS Cascading and Inheritance Level 4</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <a href="revert"><code>revert</code></a> keyword, which allows rolling a property back a cascade level.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-cascade-3/">CSS Cascading and Inheritance Level 3</a></td><td><span class="spec-rec">Recommendation</span></td><td>Removed the override cascade origin, as it was never used in a W3C standard.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/cascade.html">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'the cascade' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#the-cascade">CSS Level 1<br />
<span class="small">The definition of 'the cascade' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- [A very simple introduction to the CSS cascade](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade</a>
