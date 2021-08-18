# box-pack

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

This is a property of the original CSS Flexible Box Layout Module draft, and has been replaced by a newer standard. See [flexbox](css_flexible_box_layout/basic_concepts_of_flexbox) for information about the current standard.

The `-moz-box-pack` and `-webkit-box-pack` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) properties specify how a `-moz-box` or `-webkit-box` packs its contents in the direction of its layout. The effect of this is only visible if there is extra space in the box.

    /* Keyword values */
    box-pack: start;
    box-pack: center;
    box-pack: end;
    box-pack: justify;

    /* Global values */
    box-pack: inherit;
    box-pack: initial;
    box-pack: unset;

The direction of layout depends on the element's orientation: horizontal or vertical.

## Syntax

The `box-pack` property is specified as one of the keyword values listed below.

### Values

`start`  
The box packs contents at the start, leaving any extra space at the end.

`center`  
The box packs contents in the center, dividing any extra space equally between the start and the end.

`end`  
The box packs contents at the end, leaving any extra space at the start.

`justify`  
The space is divided evenly in-between each child, with none of the extra space placed before the first child or after the last child. If there is only one child, treat the value as if it were `start`.

## Notes

The edge of the box designated the _start_ for packing purposes depends on the box's orientation and direction:

<table><thead><tr class="header"><th></th><th><strong>Normal</strong></th><th><strong>Reverse</strong></th></tr></thead><tbody><tr class="odd"><td><strong>Horizontal</strong></td><td>left</td><td>right</td></tr><tr class="even"><td><strong>Vertical</strong></td><td>top</td><td>bottom</td></tr></tbody></table>

The edge opposite to the start is designated the _end_.

If the packing is set using the element's `pack` attribute, then the style is ignored.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>start</code></td></tr><tr class="even"><td>Applies to</td><td>elements with a CSS <a href="display"><code>display</code></a> value of <code>-moz-box</code>, <code>-moz-inline-box</code>, <code>-webkit-box</code> or <code>-webkit-inline-box</code></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    start | center | end | justify

## Examples

### Examples of box-pack

    div.example {
      border-style: solid;

      display: -moz-box; /* Mozilla */
      display: -webkit-box; /* WebKit */

      /* Make this box taller than the children,
         so there is room for the box-pack */
      height: 300px;
      /* Make this box wide enough to show the contents
         are centered horizontally */
      width: 300px;

      /* Children should be oriented vertically */
      -moz-box-orient: vertical; /* Mozilla */
      -webkit-box-orient: vertical; /* WebKit */

      /* Align children to the horizontal center of this box */
      -moz-box-align: center; /* Mozilla */
      -webkit-box-align: center; /* WebKit */

      /* Pack children to the bottom of this box */
      -moz-box-pack: end;             /* Mozilla */
      -webkit-box-pack: end;          /* WebKit */
    }

    div.example p {
      /* Make children narrower than their parent,
         so there is room for the box-align */
      width: 200px;
    }

    <div class="example">
      <p>I will be second from the bottom of div.example, centered horizontally.</p>
      <p>I will be on the bottom of div.example, centered horizontally.</p>
    </div>

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

`box-pack`

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
- [`box-direction`](box-direction)
- [`box-align`](box-align)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/box-pack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/box-pack</a>
