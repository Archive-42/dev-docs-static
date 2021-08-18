# Inheritance

In CSS, **inheritance** controls what happens when no value is specified for a property on an element.

CSS properties can be categorized in two types:

- **inherited properties**, which by default are set to the [computed value](computed_value) of the parent element
- **non-inherited properties**, which by default are set to [initial value](initial_value) of the property

Refer to [any CSS property](reference#keyword_index) definition to see whether a specific property inherits by default ("Inherited: yes") or not ("Inherited: no").

## Inherited properties

When no value for an **inherited property** has been specified on an element, the element gets the [computed value](computed_value) of that property on its parent element. Only the root element of the document gets the [initial value](initial_value) given in the property's summary.

A typical example of an inherited property is the [`color`](color) property. Given the style rules:

    p { color: green; }

... and the markup:

    <p>This paragraph has <em>emphasized text</em> in it.</p>

... the words "emphasized text" will appear green, since the `em` element has inherited the value of the [`color`](color) property from the `p` element. It does _not_ get the initial value of the property (which is the color that is used for the root element when the page specifies no color).

## Non-inherited properties

When no value for a **non-inherited property** has been specified on an element, the element gets the [initial value](initial_value) of that property (as specified in the property's summary).

A typical example of a non-inherited property is the [`border`](border) property. Given the style rules:

     p { border: medium solid; }

... and the markup:

      <p>This paragraph has <em>emphasized text</em> in it.</p>

... the words "emphasized text" will not have a border (since the initial value of [`border-style`](border-style) is `none`).

## Notes

The [`inherit`](inherit) keyword allows authors to explicitly specify inheritance. It works on both inherited and non-inherited properties.

You can control inheritance for all properties at once using the [`all`](all) shorthand property, which applies its value to all properties. For example:

    p {
      all: revert;
      font-size: 200%;
      font-weight: bold;
    }

This reverts the style of the paragraphs' [`font`](font) property to the user agent's default unless a user stylesheet exists, in which case that is used instead. Then it doubles the font size and applies a [`font-weight`](font-weight) of `"bold"`.

## See also

- CSS values for controlling inheritance: [`inherit`](inherit), [`initial`](initial), [`unset`](unset), and [`revert`](revert)
- [Introducing the CSS cascade](cascade)
- [Cascade and inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance</a>
