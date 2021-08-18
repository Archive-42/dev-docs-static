# -moz-outline-radius

**Scheduled for removal**

From Firefox 88 onwards, the standard [`outline`](outline) property will follow the shape of [`border-radius`](border-radius), making `-moz-outline-radius` properties redundant. As such, this property will be removed.

In Mozilla applications like Firefox, the `-moz-outline-radius` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) can be used to give an element's [`outline`](outline) rounded corners.

    /* One value */
    -moz-outline-radius: 25px;

    /* Two values */
    -moz-outline-radius: 25px 1em;

    /* Three values */
    -moz-outline-radius: 25px 1em 12%;

    /* Four values */
    -moz-outline-radius: 25px 1em 12% 4mm;

    /* Global values */
    -moz-outline-radius: inherit;
    -moz-outline-radius: initial;
    -moz-outline-radius: unset;

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`-moz-outline-radius-bottomleft`](-moz-outline-radius-bottomleft)
- [`-moz-outline-radius-bottomright`](-moz-outline-radius-bottomright)
- [`-moz-outline-radius-topleft`](-moz-outline-radius-topleft)
- [`-moz-outline-radius-topright`](-moz-outline-radius-topright)

## Syntax

### Values

Elliptical outlines and `<percentage>` values follow the syntax described in [`border-radius`](border-radius).

One, two, three or four `<outline-radius>` values, represents one of:

[`<length>`](length)  
See [`<length>`](length) for possible values.

[`<percentage>`](percentage)  
A [`<percentage>`](percentage); see [`border-radius`](border-radius) for details.

- If a single value is set, it applies to all 4 corners.
- If two values are set, the first one applies to the top-left and bottom-right corners and the second one to the top-right and bottom-left corners.
- If three values are set, the first one applies to the top-Left corner, the second one to the top-right and bottom-left corners and the third one to the bottom-right corner.
- If four values are set, the first one applies to the top-left corner, the second one to the top-right corner, the third one to the bottom-right corner and the fourth one to the bottom-left corner.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="-moz-outline-radius-topleft"><code>-moz-outline-radius-topleft</code></a>: <code>0</code></li><li><a href="-moz-outline-radius-topright"><code>-moz-outline-radius-topright</code></a>: <code>0</code></li><li><a href="-moz-outline-radius-bottomright"><code>-moz-outline-radius-bottomright</code></a>: <code>0</code></li><li><a href="-moz-outline-radius-bottomleft"><code>-moz-outline-radius-bottomleft</code></a>: <code>0</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="-moz-outline-radius-topleft"><code>-moz-outline-radius-topleft</code></a>: refer to the corresponding dimension of the border box</li><li><a href="-moz-outline-radius-topright"><code>-moz-outline-radius-topright</code></a>: refer to the corresponding dimension of the border box</li><li><a href="-moz-outline-radius-bottomright"><code>-moz-outline-radius-bottomright</code></a>: refer to the corresponding dimension of the border box</li><li><a href="-moz-outline-radius-bottomleft"><code>-moz-outline-radius-bottomleft</code></a>: refer to the corresponding dimension of the border box</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="-moz-outline-radius-topleft"><code>-moz-outline-radius-topleft</code></a>: as specified</li><li><a href="-moz-outline-radius-topright"><code>-moz-outline-radius-topright</code></a>: as specified</li><li><a href="-moz-outline-radius-bottomright"><code>-moz-outline-radius-bottomright</code></a>: as specified</li><li><a href="-moz-outline-radius-bottomleft"><code>-moz-outline-radius-bottomleft</code></a>: as specified</li></ul></td></tr><tr class="even"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="-moz-outline-radius-topleft"><code>-moz-outline-radius-topleft</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="-moz-outline-radius-topright"><code>-moz-outline-radius-topright</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="-moz-outline-radius-bottomright"><code>-moz-outline-radius-bottomright</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="-moz-outline-radius-bottomleft"><code>-moz-outline-radius-bottomleft</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li></ul></td></tr></tbody></table>

## Formal syntax

    <outline-radius>{1,4} [ / <outline-radius>{1,4} ]?where
    <outline-radius> = <length> | <percentage>

## Examples

### Rounding an outline

Note: This example will not display the desired effect if you are viewing this in a browser other than Firefox.

#### HTML

    <p>This element has a rounded outline!</p>

#### CSS

    p {
      margin: 5px;
      border: 1px solid black;
      outline: dotted red;
      -moz-outline-radius: 12% 1em 25px;
    }

#### Result

## Notes

- `dotted` or `dashed` radiused corners were rendered as solid until Firefox 50, [bug 382721](https://bugzilla.mozilla.org/show_bug.cgi?id=382721)
- Future versions of Gecko/Firefox may drop this property completely. See [bug 593717](https://bugzilla.mozilla.org/show_bug.cgi?id=593717).

## Specifications

Not part of any standard.

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

`-moz-outline-radius`

No

No

1-88

From Firefox 88, [outline](https://developer.mozilla.org/docs/Web/CSS/outline) now follows the shape created by [border-radius](https://developer.mozilla.org/docs/Web/CSS/border-radius) automatically, so this property is no longer needed (see [bug 1694146](https://bugzil.la/1694146)).

No

No

No

No

No

4-88

From Firefox 88, [outline](https://developer.mozilla.org/docs/Web/CSS/outline) now follows the shape created by [border-radius](https://developer.mozilla.org/docs/Web/CSS/border-radius) automatically, so this property is no longer needed (see [bug 1694146](https://bugzil.la/1694146)).

No

No

No

## See also

- [Mozilla CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions)
- Related CSS properties:
  - `outline`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius</a>
