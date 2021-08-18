# border-top-color

The `border-top-color` CSS property sets the color of an element's top [border](border). It can also be set with the shorthand CSS properties [`border-color`](border-color) or [`border-top`](border-top).

## Syntax

    /* <color> values */
    border-top-color: red;
    border-top-color: #ffbb00;
    border-top-color: rgb(255, 0, 0);
    border-top-color: hsla(100%, 50%, 25%, 0.75);
    border-top-color: currentcolor;
    border-top-color: transparent;

    /* Global values */
    border-top-color: inherit;
    border-top-color: initial;
    border-top-color: unset;

The `border-top-color` property is specified as a single value.

### Values

[`<color>`](color_value)  
The color of the top border.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    <color>where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### A simple div with a border

#### HTML

    <div class="mybox">
      <p>This is a box with a border around it.
         Note which side of the box is
         <span class="redtext">red</span>.</p>
    </div>

#### CSS

    .mybox {
      border: solid 0.3em gold;
      border-top-color: red;
      width: auto;
    }

    .redtext {
      color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#propdef-border-top-color">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-top-color' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant changes, though the <code>transparent</code> keyword, now included in <a href="color_value"><code>&lt;color&gt;</code></a> which has been extended, has been formally removed.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#propdef-border-top-color">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-top-color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-top-color`

1

12

1

Firefox also supports the non-standard [`-moz-border-top-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-top-colors) CSS property that sets the top border to multiple colors.

4

3.5

1

1

18

4

Firefox also supports the non-standard [`-moz-border-top-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-top-colors) CSS property that sets the top border to multiple colors.

10.1

1

1.0

## See also

- The border-related CSS shorthand properties: [`border`](border), [`border-top`](border-top), and [`border-color`](border-color).
- The color-related CSS properties for the other borders: [`border-right-color`](border-right-color), [`border-bottom-color`](border-bottom-color), and [`border-left-color`](border-left-color).
- The other border-related CSS properties applying to the same border: [`border-top-style`](border-top-style) and [`border-top-width`](border-top-width).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-color</a>
