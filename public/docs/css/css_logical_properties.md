# CSS Logical Properties and Values

**CSS Logical Properties and Values** is a module of [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) introducing logical properties and values that provide the ability to control layout through logical, rather than physical, direction and dimension mappings.

The module also defines logical properties and values for properties previously defined in CSS 2.1. Logical properties define direction‐relative equivalents of their corresponding physical properties.

### Block vs. inline

Logical properties and values use the abstract terms _block_ and _inline_ to describe the direction in which they flow. The physical meaning of these terms depends on the [writing mode](css_writing_modes).

Block dimension  
The dimension perpendicular to the flow of text within a line, i.e., the vertical dimension in horizontal writing modes, and the horizontal dimension in vertical writing modes. For standard English text, it is the vertical dimension.

Inline dimension  
The dimension parallel to the flow of text within a line, i.e., the horizontal dimension in horizontal writing modes, and the vertical dimension in vertical writing modes. For standard English text, it is the horizontal dimension.

## Reference

### Properties for sizing

- [`block-size`](block-size)
- [`inline-size`](inline-size)
- [`max-block-size`](max-block-size)
- [`max-inline-size`](max-inline-size)
- [`min-block-size`](min-block-size)
- [`min-inline-size`](min-inline-size)

### Properties for margins, borders and padding

- [`border-block`](border-block)
- [`border-block-color`](border-block-color)
- [`border-block-end`](border-block-end)
- [`border-block-end-color`](border-block-end-color)
- [`border-block-end-style`](border-block-end-style)
- [`border-block-end-width`](border-block-end-width)
- [`border-block-start`](border-block-start)
- [`border-block-start-color`](border-block-start-color)
- [`border-block-start-style`](border-block-start-style)
- [`border-block-start-width`](border-block-start-width)
- [`border-block-style`](border-block-style)
- [`border-block-width`](border-block-width)
- [`border-color`](border-color) <span style="white-space: nowrap;">(`logical` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> keyword)</span>
- [`border-inline`](border-inline)
- [`border-inline-color`](border-inline-color)
- [`border-inline-end`](border-inline-end)
- [`border-inline-end-color`](border-inline-end-color)
- [`border-inline-end-style`](border-inline-end-style)
- [`border-inline-end-width`](border-inline-end-width)
- [`border-inline-start`](border-inline-start)
- [`border-inline-start-color`](border-inline-start-color)
- [`border-inline-start-style`](border-inline-start-style)
- [`border-inline-start-width`](border-inline-start-width)
- [`border-inline-style`](border-inline-style)
- [`border-inline-width`](border-inline-width)
- [`border-start-start-radius`](border-start-start-radius)
- [`border-start-end-radius`](border-start-end-radius)
- [`border-end-start-radius`](border-end-start-radius)
- [`border-end-end-radius`](border-end-end-radius)
- [`border-style`](border-style) <span style="white-space: nowrap;">(`logical` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> keyword)</span>
- [`border-width`](border-width) <span style="white-space: nowrap;">(`logical` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> keyword)</span>
- [`margin`](margin) <span style="white-space: nowrap;">(`logical` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> keyword)</span>
- [`margin-block`](margin-block)
- [`margin-block-end`](margin-block-end)
- [`margin-block-start`](margin-block-start)
- [`margin-inline`](margin-inline)
- [`margin-inline-end`](margin-inline-end)
- [`margin-inline-start`](margin-inline-start)
- [`padding`](padding) <span style="white-space: nowrap;">(`logical` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> keyword)</span>
- [`padding-block`](padding-block)
- [`padding-block-end`](padding-block-end)
- [`padding-block-start`](padding-block-start)
- [`padding-inline`](padding-inline)
- [`padding-inline-end`](padding-inline-end)
- [`padding-inline-start`](padding-inline-start)

### Properties for floating and positioning

- [`clear`](clear) (`inline-end` and <span style="white-space: nowrap;">`inline-start` keywords)</span>
- [`float`](float) (`inline-end` and <span style="white-space: nowrap;">`inline-start` keywords)</span>
- [`inset`](inset)
- [`inset-block`](inset-block)
- [`inset-block-end`](inset-block-end)
- [`inset-block-start`](inset-block-start)
- [`inset-inline`](inset-inline)
- [`inset-inline-end`](inset-inline-end)
- [`inset-inline-start`](inset-inline-start)

### Other properties

- [`caption-side`](caption-side) (`inline-end` and <span style="white-space: nowrap;">`inline-start` keywords)</span>
- [`overflow-block`](overflow-block)
- [`overflow-inline`](overflow-inline)
- [`overscroll-behavior-block`](overscroll-behavior-block)
- [`overscroll-behavior-inline`](overscroll-behavior-inline)
- [`resize`](resize) (`block` and <span style="white-space: nowrap;">`inline` keywords)</span>
- [`text-align`](text-align) (`end` and <span style="white-space: nowrap;">`start` keywords)</span>

### Deprecated properties

- [`offset-block-end`](inset-block-end) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span style="white-space: nowrap;">(now [`inset-block-end`](inset-block-end) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>)</span>
- [`offset-block-start`](inset-block-start) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span style="white-space: nowrap;">(now [`inset-block-start`](inset-block-start) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>)</span>
- [`offset-inline-end`](inset-inline-end) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span style="white-space: nowrap;">(now [`inset-inline-end`](inset-inline-end) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>)</span>
- [`offset-inline-start`](inset-inline-start) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span style="white-space: nowrap;">(now [`inset-inline-start`](inset-inline-start) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>)</span>

## Guides

- [Basic concepts of logical properties and values](css_logical_properties/basic_concepts)
- [Logical Properties for sizing](css_logical_properties/sizing)
- [Logical Properties for margins, borders and padding](css_logical_properties/margins_borders_padding)
- [Logical Properties for floating and positioning](css_logical_properties/floating_and_positioning)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/">CSS Logical Properties and Values Level 1</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

- Firefox has support for the mapped properties — where there is a direct mapping from the physical to the logical version.
- Chrome, from version 69, has support for the mapped properties.
- Edge, from version 79, has the same support as Chrome.
- Firefox 66 introduces support for two value shorthands, also behind a flag in Chrome.
- Internet Explorer has no support.

See the individual property pages for full compatibility information.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties</a>
