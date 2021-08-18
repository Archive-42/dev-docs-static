# Computed value

The **computed value** of a [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is the value that is transferred from parent to child during inheritance. It is calculated from the [specified value](specified_value) by:

1.  Handling the special values [`inherit`](inherit), [`initial`](initial), [`unset`](unset), and [`revert`](revert).
2.  Doing the computation needed to reach the value described in the "Computed value" line in the property's definition table.

The computation needed to reach a property's computed value typically involves converting relative values (such as those in `em` units or percentages) to absolute values. For example, if an element has specified values `font-size: 16px` and `padding-top: 2em`, then the computed value of `padding-top` is `32px` (double the font size).

However, for some properties (those where percentages are relative to something that may require layout to determine, such as `width`, `margin-right`, `text-indent`, and `top`), percentage-specified values turn into percentage-computed values. Additionally, unitless numbers specified on the `line-height` property become the computed value, as specified. The relative values that remain in the computed value become absolute when the [used value](used_value) is determined.

**Note:** The [`getComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle) DOM API returns the [resolved value](resolved_value), which may either be the [computed value](computed_value) or the [used value](used_value), depending on the property.

## Specifications

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS22/cascade.html#computed-value">CSS Level 2 (Revision 2)<br />
<span class="small">The definition of 'computed-value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td><p>No change.</p></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/cascade.html#computed-value">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'computed value' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value</a>
