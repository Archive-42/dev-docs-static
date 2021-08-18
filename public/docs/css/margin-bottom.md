# margin-bottom

The `margin-bottom` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the [margin area](css_box_model/introduction_to_the_css_box_model) on the bottom of an element. A positive value places it farther from its neighbors, while a negative value places it closer.

<img src="data:image/svg+xml;base64,PHN2ZyBiYXNlUHJvZmlsZT0iZnVsbCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB3aWR0aD0iNDAwIiBoZWlnaHQ9IjEzMCI+PGRlZnM+PHBhdHRlcm4gaWQ9ImEiIHBhdHRlcm5Vbml0cz0idXNlclNwYWNlT25Vc2UiIHg9IjAiIHk9IjAiIHdpZHRoPSIxMDUiIGhlaWdodD0iMTA1Ij48cGF0aCBkPSJtMCA5MCAxNSAxNU0wIDc1bDMwIDMwTTAgNjBsNDUgNDVNMCA0NWw2MCA2ME0wIDMwbDc1IDc1TTAgMTVsOTAgOTBNMCAwbDEwNSAxMDVNMTUgMGw5MCA5ME0zMCAwbDc1IDc1TTQ1IDBsNjAgNjBNNjAgMGw0NSA0NU03NSAwbDMwIDMwTTkwIDBsMTUgMTUiLz48L3BhdHRlcm4+PC9kZWZzPjxwYXRoIGZpbGw9ImF6dXJlIiBkPSJNMTMwIDEwaDE0MHY5MEgxMzB6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtZGFzaGFycmF5PSIzIDIiIGZpbGw9IiNmZmYiIGQ9Ik0xNTAgMzBoMTAwdjUwSDE1MHoiLz48cGF0aCBmaWxsPSJiZWlnZSIgZD0iTTE2MCA0MGg4MHYzMGgtODB6Ii8+PHRleHQgeD0iMjkwIiB5PSIyNSIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+TWFyZ2luIGFyZWE8L3RleHQ+PHBhdGggc3Ryb2tlPSIjMDAwIiBkPSJNMjg4IDIwaC01MyIvPjx0ZXh0IHg9IjI5MCIgeT0iNDgiIGZvbnQtZmFtaWx5PSJzYW5zLXNlcmlmIiBmb250LXNpemU9IjEwcHQiPkJvcmRlcjwvdGV4dD48cGF0aCBzdHJva2U9IiMwMDAiIGQ9Ik0yNzggNDNoLTI4Ii8+PHRleHQgeD0iMjkwIiB5PSI3MSIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+Q29udGVudCBhcmVhPC90ZXh0PjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0ibTI4OCA2Ny01OC03Ii8+PHRleHQgeD0iMjkwIiB5PSI5NCIgZm9udC1mYW1pbHk9InNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMTBwdCI+UGFkZGluZyBhcmVhPC90ZXh0PjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0ibTI4OCA5MS01My0xNiIvPjxwYXRoIGZpbGw9InVybCgjYSkiIHN0cm9rZT0iIzAwMCIgZD0iTTEzMCA4MGgxNDB2MjBIMTMweiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgZD0iTTIwMCA5MHYyNSIvPjx0ZXh0IHg9IjQyIiB5PSIxMjUiIGZvbnQtZmFtaWx5PSJzYW5zLXNlcmlmIiBmb250LXNpemU9IjEwcHQiPlRoZSBoZWlnaHQgb2YgdGhpcyBhcmVhIGlzIGRlZmluZWQgYnkgdGhlIG1hcmdpbi1ib3R0b20gdmFsdWU8L3RleHQ+PHBhdGggc3Ryb2tlPSIjMDAwIiBkPSJNMTE2IDEwMGg4bS04LTIwaDhtLTQgMHYyMCIvPjx0ZXh0IHg9IjEwIiB5PSI5MyIgZm9udC1mYW1pbHk9Iidjb3VyaWVyIG5ldycsbW9ub3NwYWNlIiBmb250LXNpemU9IjEwcHQiPm1hcmdpbi1ib3R0b208L3RleHQ+PC9zdmc+" alt="The effect of the CSS margin-bottom property on the element box" width="400" height="130" />

This property has no effect on _non-[replaced](replaced_element)_ inline elements, such as [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) or [`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code).

## Syntax

    /* <length> values */
    margin-bottom: 10px;  /* An absolute length */
    margin-bottom: 1em;   /* relative to the text size */
    margin-bottom: 5%;    /* relative to the nearest block container's width */

    /* Keyword values */
    margin-bottom: auto;

    /* Global values */
    margin-bottom: inherit;
    margin-bottom: initial;
    margin-bottom: unset;

The `margin-bottom` property is specified as the keyword `auto`, or a `<length>`, or a `<percentage>`. Its value can be positive, zero, or negative.

### Values

[`<length>`](length)  
The size of the margin as a fixed value.

[`<percentage>`](percentage)  
The size of the margin as a percentage, relative to the _width_ of the containing block.

`auto`  
The browser selects a suitable value to use. See [`margin`](margin).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except elements with table <a href="display"><code>display</code></a> types other than <code>table-caption</code>, <code>table</code> and <code>inline-table</code>. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <length> | <percentage> | auto

## Examples

### Setting positive and negative bottom margins

#### HTML

    <div class="container">
    <div class="box0">Box 0</div>
    <div class="box1">Box 1</div>
    <div class="box2">Box one's negative margin pulls me up</div>
    </div>

#### CSS

CSS for divs to set margin-bottom and height

    .box0 {
        margin-bottom:1em;
        height:3em;
    }
    .box1 {
        margin-bottom:-1.5em;
        height:4em;
    }
    .box2 {
        border:1px dashed black;
        border-width:1px 0;
        margin-bottom:2em;
    }

Some definitions for container and divs so margins' effects can be seen more clearly

    .container {
        background-color:orange;
        width:320px;
        border:1px solid black;
    }
    div {
        width:320px;
        background-color:gold;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#propdef-margin-bottom">CSS Basic Box Model<br />
<span class="small">The definition of 'margin-bottom' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#margin-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'margin-bottom' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Removes its effect on inline elements.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#margin-bottom">CSS Level 1<br />
<span class="small">The definition of 'margin-bottom' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`margin-bottom`

1

12

1

3

3.5

1

1

18

4

10.1

1

1.0

`auto`

1

12

The `auto` value is not supported in quirks mode.

1

6

The `auto` value is not supported in quirks mode.

3.5

1

37

18

4

14

1

1.0

## See also

- [`margin-top`](margin-top), [`margin-right`](margin-right), and [`margin-left`](margin-left) and the [`margin`](margin) shorthand
- The mapped logical properties: [`margin-block-start`](margin-block-start), [`margin-block-end`](margin-block-end), [`margin-inline-start`](margin-inline-start), and [`margin-inline-end`](margin-inline-end) and the shorthands [`margin-block`](margin-block) and [`margin-inline`](margin-inline)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom</a>
