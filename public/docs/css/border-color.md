# border-color

The `border-color` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the color of an element's border.

Each side can be set individually using [`border-top-color`](border-top-color), [`border-right-color`](border-right-color), [`border-bottom-color`](border-bottom-color), and [`border-left-color`](border-left-color); or using the writing mode-aware [`border-block-start-color`](border-block-start-color), [`border-block-end-color`](border-block-end-color), [`border-inline-start-color`](border-inline-start-color), and [`border-inline-end-color`](border-inline-end-color).

You can find more information about border colors in [Borders](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color#borders) in [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`border-bottom-color`](border-bottom-color)
- [`border-left-color`](border-left-color)
- [`border-right-color`](border-right-color)
- [`border-top-color`](border-top-color)

## Syntax

    /* <color> values */
    border-color: red;

    /* top and bottom | left and right */
    border-color: red #f015ca;

    /* top | left and right | bottom */
    border-color: red rgb(240,30,50,.7) green;

    /* top | right | bottom | left */
    border-color: red yellow green blue;

    /* Global values */
    border-color: inherit;
    border-color: initial;
    border-color: unset;

The `border-color` property may be specified using one, two, three, or four values.

- When **one** value is specified, it applies the same color to **all four sides**.
- When **two** values are specified, the first color applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first color applies to the **top**, the second to the **left and right**, the third to the **bottom**.
- When **four** values are specified, the colors apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

[`<color>`](color_value)  
Defines the color of the border.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-top-color"><code>border-top-color</code></a>: <code>currentcolor</code></li><li><a href="border-right-color"><code>border-right-color</code></a>: <code>currentcolor</code></li><li><a href="border-bottom-color"><code>border-bottom-color</code></a>: <code>currentcolor</code></li><li><a href="border-left-color"><code>border-left-color</code></a>: <code>currentcolor</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-color"><code>border-bottom-color</code></a>: computed color</li><li><a href="border-left-color"><code>border-left-color</code></a>: computed color</li><li><a href="border-right-color"><code>border-right-color</code></a>: computed color</li><li><a href="border-top-color"><code>border-top-color</code></a>: computed color</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="border-bottom-color"><code>border-bottom-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-left-color"><code>border-left-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-right-color"><code>border-right-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="border-top-color"><code>border-top-color</code></a>: a <a href="color_value#interpolation">color</a></li></ul></td></tr></tbody></table>

## Formal syntax

    <color>{1,4}where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Complete border-color usage

#### HTML

    <div id="justone">
      <p><code>border-color: red;</code> is equivalent to</p>
      <ul><li><code>border-top-color: red;</code></li>
        <li><code>border-right-color: red;</code></li>
        <li><code>border-bottom-color: red;</code></li>
        <li><code>border-left-color: red;</code></li>
      </ul>
    </div>
    <div id="horzvert">
      <p><code>border-color: gold red;</code> is equivalent to</p>
      <ul><li><code>border-top-color: gold;</code></li>
        <li><code>border-right-color: red;</code></li>
        <li><code>border-bottom-color: gold;</code></li>
        <li><code>border-left-color: red;</code></li>
      </ul>
    </div>
    <div id="topvertbott">
      <p><code>border-color: red cyan gold;</code> is equivalent to</p>
      <ul><li><code>border-top-color: red;</code></li>
        <li><code>border-right-color: cyan;</code></li>
        <li><code>border-bottom-color: gold;</code></li>
        <li><code>border-left-color: cyan;</code></li>
      </ul>
    </div>
    <div id="trbl">
      <p><code>border-color: red cyan black gold;</code> is equivalent to</p>
      <ul><li><code>border-top-color: red;</code></li>
        <li><code>border-right-color: cyan;</code></li>
        <li><code>border-bottom-color: black;</code></li>
        <li><code>border-left-color: gold;</code></li>
      </ul>
    </div>

#### CSS

    #justone {
      border-color: red;
    }

    #horzvert {
      border-color: gold red;
    }

    #topvertbott {
      border-color: red cyan gold;
    }

    #trbl {
      border-color: red cyan black gold;
    }

    /* Set width and style for all divs */
    div {
      border: solid 0.3em;
      width: auto;
      margin: 0.5em;
      padding: 0.5em;
    }

    ul {
      margin: 0;
      list-style: none;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#logical-shorthand-keyword">CSS Logical Properties and Values Level 1</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Added the <code>logical</code> keyword.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#border-color">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-color' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The <code>transparent</code> keyword has been removed as it is now a part of the <a href="color_value"><code>&lt;color&gt;</code></a> data type.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/box.html#border-color-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The property is now a shorthand property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#border-color">CSS Level 1<br />
<span class="small">The definition of 'border-color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border-color`

1

12

1

Firefox also supports the following non-standard CSS properties to set the border sides to multiple colors: [`-moz-border-top-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-top-colors), [`-moz-border-right-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-right-colors), [`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors), [`-moz-border-left-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-left-colors)

4

3.5

1

4

18

4

Firefox also supports the following non-standard CSS properties to set the border sides to multiple colors: [`-moz-border-top-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-top-colors), [`-moz-border-right-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-right-colors), [`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors), [`-moz-border-left-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-left-colors)

10.1

1

1.0

## See also

- Border-color related CSS properties: [`border`](border), [`border-top-color`](border-top-color), [`border-right-color`](border-right-color), [`border-bottom-color`](border-bottom-color), [`border-left-color`](border-left-color),
- Other border-related CSS properties: [`border-width`](border-width), [`border-style`](border-style)
- The [`<color>`](color_value) data type
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-color</a>
