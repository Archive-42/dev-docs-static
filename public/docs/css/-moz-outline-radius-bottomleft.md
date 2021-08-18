# -moz-outline-radius-bottomleft

**Scheduled for removal**

From Firefox 88 onwards, the standard [`outline`](outline) property will follow the shape of [`border-radius`](border-radius), making `-moz-outline-radius` properties redundant. As such, this property will be removed.

In Mozilla applications, the `-moz-outline-radius-bottomleft` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property can be used to round the bottom-left corner of an element's [`outline`](outline).

## Syntax

The value of `-moz-outline-radius-bottomleft` is either a CSS [`<length>`](length) or a [percentage](percentage) of the corresponding dimensions of the border box. The [`calc()`](<calc()>) function may be used as well.

### Values

`<length>`  
The radius of the circle defining the curvature of the bottom and left edges of the element, specified as a CSS [`<length>`](length).

`<percentage>`  
The radius of the circle defining the rounding of the bottom-left corner of the element, specified as the [percentages](percentage) of the bottom and left sides of the border box.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the corresponding dimension of the border box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <outline-radius>where
    <outline-radius> = <length> | <percentage>

## Examples

### Rounding a outline

Since this is a Firefox-only property, this example will not display the desired effect if you are viewing this in a browser other than Firefox.

#### HTML

    <p>Look at this paragraph's bottom-left corner.</p>

#### CSS

    p {
      margin: 10px;
      border: solid cyan;
      outline: dotted green;
      -moz-outline-radius-bottomleft: 2em;
    }

#### Result

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

`-moz-outline-radius-bottomleft`

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

- See the [`-moz-outline-radius`](-moz-outline-radius) property for more information.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius-bottomleft" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius-bottomleft</a>
