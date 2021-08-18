# -moz-image-region

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

For certain XUL elements and pseudo-elements that use an image from the [`list-style-image`](list-style-image) property, this property specifies a region of the image that is used in place of the whole image. This allows elements to use different pieces of the same image to improve performance.

    /* Keyword value */
    -moz-image-region: auto;

    /* <shape> value */
    -moz-image-region: rect(0, 8px, 4px, 4px);

    /* Global values */
    -moz-image-region: inherit;
    -moz-image-region: initial;
    -moz-image-region: unset;

The syntax is similar to the [`clip`](clip) property. All four values are relative to the upper left corner of the image.

**Note:** For a system that works on any background, see [`-moz-image-rect()`](-moz-image-rect).

## Syntax

### Values

`auto`  
Automatically defines the region of the image to use.

[`<shape>`](shape)  
A shape defining the part of the image to use. The `rect()` function defines a rectangle to use as shape. Its parameters define the top, right, bottom, and left offsets of the edges of the image, in this order.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>XUL <a href="image"><code>&lt;image&gt;</code></a> elements and <a href=":-moz-tree-image"><code>:-moz-tree-image</code></a>, <a href=":-moz-tree-twisty"><code>:-moz-tree-twisty</code></a>, and <a href=":-moz-tree-checkbox"><code>:-moz-tree-checkbox</code></a> pseudo-elements. <strong>Note:</strong> <code>-moz-image-region</code> only works with <a href="image"><code>&lt;image&gt;</code></a> elements where the icon is specified using <a href="list-style-image"><code>list-style-image</code></a>. It will not work with XUL <code>&lt;image src="url" /&gt;</code>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <shape> | autowhere
    <shape> = rect(<top>, <right>, <bottom>, <left>)

## Examples

### Clipping an image

    #example-button {
      /* display only the 4x4 area from the top left of this image */
      list-style-image: url("chrome://example/skin/example.png");
      -moz-image-region: rect(0px, 4px, 4px, 0px);
    }
    #example-button:hover {
      /* use the 4x4 area to the right of the first for the hovered button */
      -moz-image-region: rect(0px, 8px, 4px, 4px);
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

`-moz-image-region`

No

No

1

No

No

No

No

No

4

No

No

No

## See also

- [`-moz-image-rect()`](-moz-image-rect)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-image-region" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-image-region</a>
