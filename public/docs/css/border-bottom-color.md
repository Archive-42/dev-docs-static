# border-bottom-color

The `border-bottom-color` CSS property sets the color of an element's bottom [border](border). It can also be set with the shorthand CSS properties [`border-color`](border-color) or [`border-bottom`](border-bottom).

## Syntax

    /* <color> values */
    border-bottom-color: red;
    border-bottom-color: #ffbb00;
    border-bottom-color: rgb(255, 0, 0);
    border-bottom-color: hsla(100%, 50%, 25%, 0.75);
    border-bottom-color: currentcolor;
    border-bottom-color: transparent;

    /* Global values */
    border-bottom-color: inherit;
    border-bottom-color: initial;
    border-bottom-color: unset;

The `border-bottom-color` property is specified as a single value.

### Values

[`<color>`](color_value)  
The color of the bottom border.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    <'border-top-color'>

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
        border-bottom-color: red;
        width: auto;
    }

    .redtext {
        color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#propdef-border-bottom-color">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-bottom-color' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant changes, though the <code>transparent</code> keyword, now included in <a href="color_value"><code>&lt;color&gt;</code></a> which has been extended, has been formally removed.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#propdef-border-bottom-color">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-bottom-color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`border-bottom-color`

1

12

1

Firefox also supports the non-standard [`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors) CSS property that sets the bottom border to multiple colors.

4

3.5

1

1

18

4

Firefox also supports the non-standard [`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors) CSS property that sets the bottom border to multiple colors.

10.1

1

1.0

## See also

- The border-related CSS shorthand properties: [`border`](border), [`border-bottom`](border-bottom), and [`border-color`](border-color).
- The color-related CSS properties for the other borders: [`border-right-color`](border-right-color), [`border-top-color`](border-top-color), and [`border-left-color`](border-left-color).
- The other border-related CSS properties applying to the same border: [`border-bottom-style`](border-bottom-style) and [`border-bottom-width`](border-bottom-width).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-color</a>
