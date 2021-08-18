# box-direction

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

This is a property of the original CSS Flexible Box Layout Module draft, and has been replaced by a newer standard. The `-moz-box-direction` will only be used for XUL while the previous standard `box-direction` has been replaced by `flex-direction`. See [flexbox](css_flexible_box_layout/basic_concepts_of_flexbox) for information about the current standard.

The `box-direction` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies whether a box lays out its contents normally (from the top or left edge), or in reverse (from the bottom or right edge).

    /* Keyword values */
    box-direction: normal;
    box-direction: reverse;

    /* Global values */
    box-direction: inherit;
    box-direction: initial;
    box-direction: unset;

## Syntax

The `box-direction` property is specified as one of the keyword values listed below.

### Values

`normal`  
The box lays out its contents from the start (the left or top edge).

`reverse`  
The box lays out its contents from the end (the right or bottom edge).

## Notes

The edge of the box designated the _start_ for layout purposes depends on the box's orientation:

<table><tbody><tr class="odd"><td><strong>Horizontal</strong></td><td>left</td></tr><tr class="even"><td><strong>Vertical</strong></td><td>top</td></tr></tbody></table>

The edge opposite to the start is designated the _end_.

If the direction is set using the element's `dir` attribute, then the style is ignored.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>elements with a CSS <a href="display"><code>display</code></a> value of <code>box</code> or <code>inline-box</code></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | reverse | inherit

## Examples

### Setting box direction

    .example {
      /* bottom-to-top layout */
      -moz-box-direction: reverse;      /* Mozilla */
      -webkit-box-direction: reverse;   /* WebKit */
      box-direction: reverse;           /* As specified */
    }

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

`box-direction`

1

12

1

49

48

No

15

3

1.1-3

≤37

18

4

49

48

14

1

1.0

## See also

- [`box-orient`](box-orient)
- [`box-pack`](box-pack)
- [`box-align`](box-align)
- [`flex-direction`](flex-direction)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/box-direction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/box-direction</a>
