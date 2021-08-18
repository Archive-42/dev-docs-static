# padding-bottom

The `padding-bottom` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the height of the [padding area](css_box_model/introduction_to_the_css_box_model#padding-area) on the bottom of an element.

An element's padding area is the space between its content and its border.

<img src="data:image/svg+xml;base64,PHN2ZyBiYXNlUHJvZmlsZT0iZnVsbCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iNDAwIiBoZWlnaHQ9IjEzMCI+PGRlZnM+PHBhdHRlcm4gaWQ9ImEiIHBhdHRlcm5Vbml0cz0idXNlclNwYWNlT25Vc2UiIHg9IjAiIHk9IjAiIHdpZHRoPSIxMDUiIGhlaWdodD0iMTA1Ij48cGF0aCBkPSJtMCA5MCAxNSAxNU0wIDc1bDMwIDMwTTAgNjBsNDUgNDVNMCA0NWw2MCA2ME0wIDMwbDc1IDc1TTAgMTVsOTAgOTBNMCAwbDEwNSAxMDVNMTUgMGw5MCA5ME0zMCAwbDc1IDc1TTQ1IDBsNjAgNjBNNjAgMGw0NSA0NU03NSAwbDMwIDMwTTkwIDBsMTUgMTUiLz48L3BhdHRlcm4+PC9kZWZzPjxwYXRoIGZpbGw9ImF6dXJlIiBkPSJNMTMwIDEwaDE0MHY5MEgxMzB6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtZGFzaGFycmF5PSIzIDIiIGZpbGw9IiNmZmYiIGQ9Ik0xNTAgMzBoMTAwdjUwSDE1MHoiLz48cGF0aCBmaWxsPSJiZWlnZSIgZD0iTTE2MCA0MGg4MHYzMGgtODB6Ii8+PHRleHQgeD0iMjkwIiB5PSIyNCIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+UGFkZGluZyBhcmVhPC90ZXh0PjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0iTTI4OCA5M2gtMzMiLz48dGV4dCB4PSIyOTAiIHk9IjQ4IiBmb250LWZhbWlseT0ic2Fucy1zZXJpZiIgZm9udC1zaXplPSIxMHB0Ij5Cb3JkZXI8L3RleHQ+PHBhdGggc3Ryb2tlPSIjMDAwIiBkPSJNMjg4IDQ0aC0zOCIvPjx0ZXh0IHg9IjI5MCIgeT0iNzEiIGZvbnQtZmFtaWx5PSJzYW5zLXNlcmlmIiBmb250LXNpemU9IjEwcHQiPkNvbnRlbnQgYXJlYTwvdGV4dD48cGF0aCBzdHJva2U9IiMwMDAiIGQ9Im0yODggNjctNTgtNyIvPjx0ZXh0IHg9IjI5MCIgeT0iOTciIGZvbnQtZmFtaWx5PSJzYW5zLXNlcmlmIiBmb250LXNpemU9IjEwcHQiPk1hcmdpbiBhcmVhPC90ZXh0PjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0ibTI4OCAyMC01MyAxNSIvPjxwYXRoIGZpbGw9InVybCgjYSkiIHN0cm9rZT0iIzAwMCIgZD0iTTE1MCA3MGgxMDB2MTBIMTUweiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0iTTIwMCAxMDVWNzUiLz48dGV4dCB4PSIyMiIgeT0iMTIwIiBmb250LWZhbWlseT0ic2Fucy1zZXJpZiIgZm9udC1zaXplPSIxMHB0Ij5UaGUgaGVpZ2h0IG9mIHRoaXMgYXJlYSBpcyBkZWZpbmVkIGJ5IHRoZSBwYWRkaW5nLWJvdHRvbSB2YWx1ZTwvdGV4dD48cGF0aCBzdHJva2U9IiMwMDAiIGQ9Ik0xMzYgNzBoOG0tOCAxMGg4bS00LTEwdjEwIi8+PHRleHQgeD0iMjAiIHk9Ijc3IiBmb250LWZhbWlseT0iJ2NvdXJpZXIgbmV3Jyxtb25vc3BhY2UiIGZvbnQtc2l6ZT0iMTBwdCI+cGFkZGluZy1ib3R0b208L3RleHQ+PC9zdmc+" alt="The effect of the CSS padding-bottom property on the element box" width="400" height="130" />

**Note:** The [`padding`](padding) property can be used to set paddings on all four sides of an element with a single declaration.

## Syntax

    /* <length> values */
    padding-bottom: 0.5em;
    padding-bottom: 0;
    padding-bottom: 2cm;

    /* <percentage> value */
    padding-bottom: 10%;

    /* Global values */
    padding-bottom: inherit;
    padding-bottom: initial;
    padding-bottom: unset;

The `padding-bottom` property is specified as a single value chosen from the list below. Unlike margins, negative values are not allowed for padding.

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

### Setting padding bottom with pixels and percentages

    .content { padding-bottom: 5%; }
    .sidebox { padding-bottom: 10px; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#propdef-padding-bottom">CSS Basic Box Model<br />
<span class="small">The definition of 'padding-bottom' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#padding-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'padding-bottom' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#padding-bottom">CSS Level 1<br />
<span class="small">The definition of 'padding-bottom' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`padding-bottom`

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
- [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-left`](padding-left) and the [`padding`](padding) shorthand
- The mapped logical properties: [`padding-block-start`](padding-block-start), [`padding-block-end`](padding-block-end), [`padding-inline-start`](padding-inline-start), and [`padding-inline-end`](padding-inline-end) and the shorthands [`padding-block`](padding-block) and [`padding-inline`](padding-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom</a>
