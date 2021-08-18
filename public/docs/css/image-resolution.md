# image-resolution

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `image-resolution` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the intrinsic resolution of all raster images used in or on the element. It affects content images such as replaced elements and generated content, and decorative images such as `background-image` images.

The image resolution is defined as the number of image pixels per unit length, e.g., pixels per inch. By default, CSS assumes a resolution of one image pixel per CSS px unit; however, the `image-resolution` property allows a different resolution to be specified.

## Syntax

    image-resolution: from-image;
    image-resolution: 300dpi;
    image-resolution: from-image 300dpi;
    image-resolution: 300dpi snap;

    /* Global values */
    image-resolution: inherit;
    image-resolution: initial;
    image-resolution: unset;

### Values

`<resolution>`  
Specifies the intrinsic resolution explicitly.

`from-image`  
Uses the intrinsic resolution as specified by the image format. If the image does not specify its own resolution, the explicitly specified resolution is used (if given), else it defaults to `1dppx` (1 image pixel per CSS px unit).

`snap`  
If the `snap` keyword is provided, the computed resolution is the specified resolution rounded to the nearest value that would map one image pixel to an integer number of device pixels. If the resolution is taken from the image, then the used intrinsic resolution is the image’s native resolution similarly adjusted.

**Note:** As vector formats such as SVG do not have an intrinsic resolution, this property has no effect on vector images.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>1dppx</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, except with &lt;resolution&gt; possibly altered by computed for 'snap' value</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ from-image || <resolution> ] && snap?

## Examples

### Setting a high dpi for print

When printing the document, use a higher resolution.

    @media print {
      .myimage {
        image-resolution: 300dpi;
      }
    }

### Use image resolution with fallback

Uses the resolution from the image. If the image does not have a resolution, use 300dpi rather than the default 1dppx.

    .myimage {
      image-resolution: from-image 300dpi;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#the-image-resolution">CSS Images Module Level 4<br />
<span class="small">The definition of 'image-resolution' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

## See also

- Other image-related CSS properties: [`object-fit`](object-fit), [`object-position`](object-position), [`image-orientation`](image-orientation), [`image-rendering`](image-rendering).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/image-resolution" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/image-resolution</a>
