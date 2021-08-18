# Specified value

The **specified value** of a [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is the value it receives from the document's style sheet. The specified value for a given property is determined according to the following rules:

1.  If the document's style sheet explicitly specifies a value for the property, the given value will be used.
2.  If the document's style sheet doesn't specify a value but it is an inherited property, the value will be taken from the parent element.
3.  If none of the above pertain, the element's [initial value](initial_value) will be used.

## Examples

### HTML

    <p>My specified color is given explicitly in the CSS.</p>

    <div>The specified values of all my properties default to their
        initial values, because none of them are given in the CSS.</div>

    <div class="fun">
      <p>The specified value of my font family is not given explicitly
          in the CSS, so it is inherited from my parent. However,
          the border is not an inheriting property.</p>
    </div>

### CSS

    .fun {
      border: 1px dotted pink;
      font-family: fantasy;
    }

    p {
      color: green;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS22/cascade.html#specified-value">CSS Level 2 (Revision 2)<br />
<span class="small">The definition of 'cascaded value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/cascade.html#specified-value">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'cascaded value' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/specified_value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/specified_value</a>
