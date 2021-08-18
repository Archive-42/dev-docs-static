# Actual value

The **actual value** of a [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is the [used value](used_value) of that property after any necessary approximations have been applied. For example, a [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that can only render borders with a whole-number pixel width may round the thickness of the border to the nearest integer.

## Calculating a property's actual value

The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) performs four steps to calculate a property's actual (final) value:

1.  First, the [specified value](specified_value) is determined based on the result of [cascading](cascade), [inheritance](inheritance), or using the [initial value](initial_value).
2.  Next, the [computed value](computed_value) is calculated according to the specification (for example, a `span` with `position: absolute` will have its computed `display` changed to `block`).
3.  Then, layout is calculated, resulting in the [used value](used_value).
4.  Finally, the used value is transformed according to the limitations of the local environment, resulting in the actual value.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/cascade.html#actual-value">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'actual value' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/actual_value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/actual_value</a>
