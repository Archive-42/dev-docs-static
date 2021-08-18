# &lt;flex&gt;

The `<flex>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) denotes a flexible length within a grid container. It is used in [`grid-template-columns`](grid-template-columns), [`grid-template-rows`](grid-template-rows) and other related properties.

## Syntax

The `<flex>` data type is specified as a [`<number>`](number) followed by the unit <span id="fr">`fr`</span>. The `fr` unit represents a fraction of the leftover space in the grid container. As with all CSS dimensions, there is no space between the unit and the number.

## Examples

### Examples of correct values for the fr data type

    1fr    /* Using an integer value */
    2.5fr  /* Using a float value */

### Example of use in a tracklisting for CSS Grid layout

    .grid {
      display: grid;
      grid-template-columns: 1fr 1fr 2.5fr 1.5fr;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid/#typedef-flex">CSS Grid Layout<br />
<span class="small">The definition of '&lt;flex&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`flex_value`

29

12

40

10

28

10.1

57

29

40

28

10.3

2.0

## See also

- [CSS Grid Layout](css_grid_layout)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value</a>
