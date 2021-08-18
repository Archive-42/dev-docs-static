# padding-top

The `padding-top` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the height of the [padding area](css_box_model/introduction_to_the_css_box_model#padding-area) on the top of an element.

An element's padding area is the space between its content and its border.

<img src="data:image/svg+xml;base64,PHN2ZyBiYXNlUHJvZmlsZT0iZnVsbCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iNDAwIiBoZWlnaHQ9IjEzMCI+PGRlZnM+PHBhdHRlcm4gaWQ9ImEiIHBhdHRlcm5Vbml0cz0idXNlclNwYWNlT25Vc2UiIHg9IjAiIHk9IjAiIHdpZHRoPSIxMDUiIGhlaWdodD0iMTA1Ij48cGF0aCBkPSJtMCA5MCAxNSAxNU0wIDc1bDMwIDMwTTAgNjBsNDUgNDVNMCA0NWw2MCA2ME0wIDMwbDc1IDc1TTAgMTVsOTAgOTBNMCAwbDEwNSAxMDVNMTUgMGw5MCA5ME0zMCAwbDc1IDc1TTQ1IDBsNjAgNjBNNjAgMGw0NSA0NU03NSAwbDMwIDMwTTkwIDBsMTUgMTUiLz48L3BhdHRlcm4+PC9kZWZzPjxwYXRoIGZpbGw9ImF6dXJlIiBkPSJNMTMwIDQwaDE0MHY5MEgxMzB6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtZGFzaGFycmF5PSIzIDIiIGZpbGw9IiNmZmYiIGQ9Ik0xNTAgNjBoMTAwdjUwSDE1MHoiLz48cGF0aCBmaWxsPSJiZWlnZSIgZD0iTTE2MCA3MGg4MHYzMGgtODB6Ii8+PHRleHQgeD0iMjkwIiB5PSIxMjQiIGZvbnQtZmFtaWx5PSJzYW5zLXNlcmlmIiBmb250LXNpemU9IjEwcHQiPlBhZGRpbmcgYXJlYTwvdGV4dD48cGF0aCBzdHJva2U9IiMwMDAiIGQ9Im0yODggMTIwLTUzLTE1Ii8+PHRleHQgeD0iMjkwIiB5PSI3OCIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+Qm9yZGVyPC90ZXh0PjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0iTTI3OCA3NGgtMjgiLz48dGV4dCB4PSIyOTAiIHk9IjEwMSIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+Q29udGVudCBhcmVhPC90ZXh0PjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0ibTI4OCA5Ny01OC03Ii8+PHRleHQgeD0iMjkwIiB5PSI1NSIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+TWFyZ2luIGFyZWE8L3RleHQ+PHBhdGggc3Ryb2tlPSIjMDAwIiBkPSJNMjg4IDUwaC01MyIvPjxwYXRoIGZpbGw9InVybCgjYSkiIHN0cm9rZT0iIzAwMCIgZD0iTTE1MCA2MGgxMDB2MTBIMTUweiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0iTTIwMCAyN3Y0MCIvPjx0ZXh0IHg9IjQyIiB5PSIyMCIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+VGhlIGhlaWdodCBvZiB0aGlzIGFyZWEgaXMgZGVmaW5lZCBieSB0aGUgcGFkZGluZy10b3AgdmFsdWU8L3RleHQ+PHBhdGggc3Ryb2tlPSIjMDAwIiBkPSJNMTM2IDYwaDhtLTggMTBoOG0tNC0xMHYxMCIvPjx0ZXh0IHg9IjM1IiB5PSI2NyIgZm9udC1mYW1pbHk9Iidjb3VyaWVyIG5ldycsbW9ub3NwYWNlIiBmb250LXNpemU9IjEwcHQiPnBhZGRpbmctdG9wPC90ZXh0Pjwvc3ZnPg==" alt="The effect of the CSS padding-top property on the element box" width="400" height="130" />

**Note:** The [`padding`](padding) property can be used to set paddings on all four sides of an element with a single declaration.

## Syntax

    /* <length> values */
    padding-top: 0.5em;
    padding-top: 0;
    padding-top: 2cm;

    /* <percentage> value */
    padding-top: 10%;

    /* Global values */
    padding-top: inherit;
    padding-top: initial;
    padding-top: unset;

The `padding-top` property is specified as a single value chosen from the list below. Unlike margins, negative values are not allowed for padding.

### Values

[`<length>`](length)  
The size of the padding as a fixed value. Must be nonnegative.

[`<percentage>`](percentage)  
The size of the padding as a percentage, relative to the _width_ of the containing block. Must be nonnegative.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except <code>table-row-group</code>, <code>table-header-group</code>, <code>table-footer-group</code>, <code>table-row</code>, <code>table-column-group</code> and <code>table-column</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <length> | <percentage>

## Examples

### Setting top padding using pixels and percentages

    .content { padding-top: 5%; }
    .sidebox { padding-top: 10px; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#propdef-padding-top">CSS Basic Box Model<br />
<span class="small">The definition of 'padding-top' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#padding-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'padding-top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#padding-top">CSS Level 1<br />
<span class="small">The definition of 'padding-top' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`padding-top`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

## See also

- [Introduction to the CSS basic box model](css_box_model/introduction_to_the_css_box_model)
- [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), [`padding-left`](padding-left) and the [`padding`](padding) shorthand
- The mapped logical properties: [`padding-block-start`](padding-block-start), [`padding-block-end`](padding-block-end), [`padding-inline-start`](padding-inline-start), and [`padding-inline-end`](padding-inline-end) and the shorthands [`padding-block`](padding-block) and [`padding-inline`](padding-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top</a>
