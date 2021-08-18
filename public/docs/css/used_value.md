# Used value

The **used value** of a [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is its value after all calculations have been performed on the [computed value](computed_value).

After the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) has finished its calculations, every CSS property has a used value. The used values of dimensions (e.g., [`width`](width), [`line-height`](line-height)) are in pixels. The used values of shorthand properties (e.g., [`background`](background)) are consistent with those of their component properties (e.g., [`background-color`](background-color) or [`background-size`](background-size)) and with [`position`](position) and [`float`](float).

**Note:** The [`getComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle) DOM API returns the [resolved value](resolved_value), which may either be the [computed value](computed_value) or the [used value](used_value), depending on the property.

## Example

This example computes and displays the used `width` value of three elements (updates on resize):

### HTML

    <div id="no-width">
      <p>No explicit width.</p>
      <p class="show-used-width">..</p>

      <div id="width-50">
        <p>Explicit width: 50%.</p>
        <p class="show-used-width">..</p>

        <div id="width-inherit">
          <p>Explicit width: inherit.</p>
          <p class="show-used-width">..</p>
        </div>
      </div>
    </div>

### CSS

    #no-width {
      width: auto;
    }

    #width-50 {
      width: 50%;
    }

    #width-inherit {
      width: inherit;
    }

    /* Make results easier to see */
    div {
      border: 1px solid red;
      padding: 8px;
    }

### JavaScript

    function updateUsedWidth(id) {
      var div = document.querySelector(`#${id}`);
      var par = div.querySelector('.show-used-width');
      var wid = window.getComputedStyle(div)["width"];
      par.textContent = `Used width: ${wid}.`;
    }

    function updateAllUsedWidths() {
      updateUsedWidth("no-width");
      updateUsedWidth("width-50");
      updateUsedWidth("width-inherit");
    }

    updateAllUsedWidths();
    window.addEventListener('resize', updateAllUsedWidths);

### Result

## Difference from computed value

CSS 2.0 defined only _computed value_ as the last step in a property's calculation. Then, CSS 2.1 introduced the distinct definition of used value. An element could then explicitly inherit a width/height of a parent, whose computed value is a percentage. For CSS properties that don't depend on layout (e.g., `display`, `font-size`, or `line-height`), the computed values and used values are the same. The following are the CSS 2.1 properties that do depend on layout, so they have a different computed value and used value: (taken from [CSS 2.1 Changes: Specified, computed, and actual values](https://www.w3.org/TR/CSS2/changes.html#q21.36)):

- `background-position`
- `bottom`, `left`, `right`, `top`
- `height`, `width`
- `margin-bottom`, `margin-left`, `margin-right`, `margin-top`
- `min-height`, `min-width`
- `padding-bottom`, `padding-left`, `padding-right`, `padding-top`
- `text-indent`

## Specifications

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS22/cascade.html#used-value">CSS Level 2 (Revision 2)<br />
<span class="small">The definition of 'used value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td><p>No change.</p></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/cascade.html#used-value">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'used value' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/used_value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/used_value</a>
