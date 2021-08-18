# border-bottom-style

The `border-bottom-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the line style of an element's bottom [`border`](border).

**Note:** The specification doesn't define how borders of different styles connect in the corners.

## Syntax

    /* Keyword values */
    border-bottom-style: none;
    border-bottom-style: hidden;
    border-bottom-style: dotted;
    border-bottom-style: dashed;
    border-bottom-style: solid;
    border-bottom-style: double;
    border-bottom-style: groove;
    border-bottom-style: ridge;
    border-bottom-style: inset;
    border-bottom-style: outset;

    /* Global values */
    border-bottom-style: inherit;
    border-bottom-style: initial;
    border-bottom-style: unset;

The `border-bottom-style` property is specified as a single keyword chosen from those available for the [`border-style`](border-style) property.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <line-style>where
    <line-style> = none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset

## Examples

### Demonstrating all border styles

#### HTML

    <table>
      <tr>
        <td class="b1">none</td>
        <td class="b2">hidden</td>
        <td class="b3">dotted</td>
        <td class="b4">dashed</td>
      </tr>
      <tr>
        <td class="b5">solid</td>
        <td class="b6">double</td>
        <td class="b7">groove</td>
        <td class="b8">ridge</td>
      </tr>
      <tr>
        <td class="b9">inset</td>
        <td class="b10">outset</td>
      </tr>
    </table>

#### CSS

    /* Define look of the table */
    table {
      border-width: 3px;
      background-color: #52E385;
    }
    tr, td {
      padding: 3px;
    }

    /* border-bottom-style example classes */
    .b1 {border-bottom-style: none;}
    .b2 {border-bottom-style: hidden;}
    .b3 {border-bottom-style: dotted;}
    .b4 {border-bottom-style: dashed;}
    .b5 {border-bottom-style: solid;}
    .b6 {border-bottom-style: double;}
    .b7 {border-bottom-style: groove;}
    .b8 {border-bottom-style: ridge;}
    .b9 {border-bottom-style: inset;}
    .b10 {border-bottom-style: outset;}

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#propdef-border-bottom-style">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-bottom-style' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#border-style-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-bottom-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border-bottom-style`

1

12

1

Prior to Firefox 50, border styles of rounded corners (with [`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius)) were always rendered as if `border-bottom-style` was `solid`. This has been fixed in Firefox 50.

5.5

9.2

1

≤37

18

4

Prior to Firefox 50, border styles of rounded corners (with [`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius)) were always rendered as if `border-bottom-style` was `solid`. This has been fixed in Firefox 50.

14

1

1.0

## See also

- The other style-related border properties: [`border-left-style`](border-left-style), [`border-right-style`](border-right-style), [`border-top-style`](border-top-style), and [`border-style`](border-style).
- The other bottom-border-related properties: [`border-bottom`](border-bottom), [`border-bottom-color`](border-bottom-color), and [`border-bottom-width`](border-bottom-width).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-style</a>
