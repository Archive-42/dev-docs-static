# border-style

The `border-style` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the line style for all four sides of an element's border.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-bottom-style`](border-bottom-style)
- [`border-left-style`](border-left-style)
- [`border-right-style`](border-right-style)
- [`border-top-style`](border-top-style)

## Syntax

    /* Keyword values */
    border-style: none;
    border-style: hidden;
    border-style: dotted;
    border-style: dashed;
    border-style: solid;
    border-style: double;
    border-style: groove;
    border-style: ridge;
    border-style: inset;
    border-style: outset;

    /* top and bottom | left and right */
    border-style: dotted solid;

    /* top | left and right | bottom */
    border-style: hidden double dashed;

    /* top | right | bottom | left */
    border-style: none solid dotted dashed;

    /* Global values */
    border-style: inherit;
    border-style: initial;
    border-style: unset;

The `border-style` property may be specified using one, two, three, or four values.

- When **one** value is specified, it applies the same style to **all four sides**.
- When **two** values are specified, the first style applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first style applies to the **top**, the second to the **left and right**, the third to the **bottom**.
- When **four** values are specified, the styles apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

Each value is a keyword chosen from the list below.

### Values

`<line-style>`  
Describes the style of the border. It can have the following values:

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><tbody><tr class="odd"><td><code>none</code></td><td></td><td>Like the <code>hidden</code> keyword, displays no border. Unless a <a href="background-image"><code>background-image</code></a> is set, the computed value of the same side's <a href="border-width"><code>border-width</code></a> will be <code>0</code>, even if the specified value is something else. In the case of table cell and border collapsing, the <code>none</code> value has the <em>lowest</em> priority: if any other conflicting border is set, it will be displayed.</td></tr><tr class="even"><td><code>hidden</code></td><td></td><td>Like the <code>none</code> keyword, displays no border. Unless a <a href="background-image"><code>background-image</code></a> is set, the computed value of the same side's <a href="border-width"><code>border-width</code></a> will be <code>0</code>, even if the specified value is something else. In the case of table cell and border collapsing, the <code>hidden</code> value has the <em>highest</em> priority: if any other conflicting border is set, it won't be displayed.</td></tr><tr class="odd"><td><code>dotted</code></td><td></td><td>Displays a series of rounded dots. The spacing of the dots is not defined by the specification and is implementation-specific. The radius of the dots is half the computed value of the same side's <a href="border-width"><code>border-width</code></a>.</td></tr><tr class="even"><td><code>dashed</code></td><td></td><td>Displays a series of short square-ended dashes or line segments. The exact size and length of the segments are not defined by the specification and are implementation-specific.</td></tr><tr class="odd"><td><code>solid</code></td><td></td><td>Displays a single, straight, solid line.</td></tr><tr class="even"><td><code>double</code></td><td></td><td>Displays two straight lines that add up to the pixel size defined by <a href="border-width"><code>border-width</code></a>.</td></tr><tr class="odd"><td><code>groove</code></td><td></td><td>Displays a border with a carved appearance. It is the opposite of <code>ridge</code>.</td></tr><tr class="even"><td><code>ridge</code></td><td></td><td>Displays a border with an extruded appearance. It is the opposite of <code>groove</code>.</td></tr><tr class="odd"><td><code>inset</code></td><td></td><td>Displays a border that makes the element appear embedded. It is the opposite of <code>outset</code>. When applied to a table cell with <a href="border-collapse"><code>border-collapse</code></a> set to <code>collapsed</code>, this value behaves like <code>groove</code>.</td></tr><tr class="even"><td><code>outset</code></td><td></td><td><p>Displays a border that makes the element appear embossed. It is the opposite of <code>inset</code>. When applied to a table cell with <a href="border-collapse"><code>border-collapse</code></a> set to <code>collapsed</code>, this value behaves like <code>ridge</code>.</p></td></tr></tbody></table>

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-style"><code>border-top-style</code></a>: <code>none</code></li><li><a href="border-right-style"><code>border-right-style</code></a>: <code>none</code></li><li><a href="border-bottom-style"><code>border-bottom-style</code></a>: <code>none</code></li><li><a href="border-left-style"><code>border-left-style</code></a>: <code>none</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-style"><code>border-bottom-style</code></a>: as specified</li><li><a href="border-left-style"><code>border-left-style</code></a>: as specified</li><li><a href="border-right-style"><code>border-right-style</code></a>: as specified</li><li><a href="border-top-style"><code>border-top-style</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <line-style>{1,4}where
    <line-style> = none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset

## Examples

### Table with all property values

Here is an example of all the property values.

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
      background-color: #52E396;
    }
    tr, td {
      padding: 2px;
    }

    /* border-style example classes */
    .b1 {border-style:none;}
    .b2 {border-style:hidden;}
    .b3 {border-style:dotted;}
    .b4 {border-style:dashed;}
    .b5 {border-style:solid;}
    .b6 {border-style:double;}
    .b7 {border-style:groove;}
    .b8 {border-style:ridge;}
    .b9 {border-style:inset;}
    .b10 {border-style:outset;}

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#border-style">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-style' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#propdef-border-style">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <code>hidden</code> keyword value.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#border-style">CSS Level 1<br />
<span class="small">The definition of 'border-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border-style`

1

12

1

Prior to Firefox 50, border styles of rounded corners were always rendered as if `border-style` was solid. This has been fixed in Firefox 50.

4

3.5

1

3

18

4

Prior to Firefox 50, border styles of rounded corners were always rendered as if `border-style` was solid. This has been fixed in Firefox 50.

14

3

1.0

## See also

- The border-related shorthand CSS properties: [`border`](border), [`border-width`](border-width), [`border-color`](border-color), [`border-radius`](border-radius)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-style</a>
