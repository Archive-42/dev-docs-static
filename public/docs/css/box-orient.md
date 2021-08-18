# box-orient

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

This is a property of the original CSS Flexible Box Layout Module draft, and has been replaced by a newer standard. See [flexbox](css_flexible_box_layout/basic_concepts_of_flexbox) for information about the current standard.

The `box-orient` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an element lays out its contents horizontally or vertically.

    /* Keyword values */
    box-orient: horizontal;
    box-orient: vertical;
    box-orient: inline-axis;
    box-orient: block-axis;

    /* Global values */
    box-orient: inherit;
    box-orient: initial;
    box-orient: unset;

## Syntax

The `box-orient` property is specified as one of the keyword values listed below.

### Values

`horizontal`  
The box lays out its contents horizontally.

`vertical`  
The box lays out its contents vertically.

`inline-axis` (HTML)  
The box displays its children along the inline axis.

`block-axis` (HTML)  
The box displays its children along the block axis.

The inline and block axes are the writing-mode dependent keywords which, in English, map to `horizontal` and `vertical` respectively.

## Description

HTML DOM elements lay out their contents along the inline-axis by default. This CSS property will only apply to HTML elements with a CSS [`display`](display) value of <span class="page-not-created">`box`</span> or <span class="page-not-created">`inline-box`</span>.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>inline-axis</code> (<code>horizontal</code> in <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL">XUL</a>)</td></tr><tr class="even"><td>Applies to</td><td>elements with a CSS <a href="display"><code>display</code></a> value of <code>box</code> or <code>inline-box</code></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    horizontal | vertical | inline-axis | block-axis | inherit

## Examples

### Setting horizontal box orientation

Here, he `box-orient` property will cause the two [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) sections in the example to display in the same line.

#### HTML

    <div class="example">
        <p>I will be to the left of my sibling.</p>
        <p>I will be to the right of my sibling.</p>
    </div>

#### CSS

    div.example {
      display: -moz-box;                /* Mozilla */
      display: -webkit-box;             /* WebKit */
      display: box;                     /* As specified */

      /* Children should be oriented vertically */
      -moz-box-orient: horizontal;      /* Mozilla */
      -webkit-box-orient: horizontal;   /* WebKit */
      box-orient: horizontal;           /* As specified */
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

`box-orient`

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

- [`box-direction`](box-direction)
- [`box-pack`](box-pack)
- [`box-align`](box-align)
- [`flex-direction`](flex-direction)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/box-orient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/box-orient</a>
