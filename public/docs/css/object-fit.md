# object-fit

The `object-fit` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how the content of a [replaced element](replaced_element), such as an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), should be resized to fit its container.

You can alter the alignment of the replaced element's content object within the element's box using the [`object-position`](object-position) property.

## Syntax

The `object-fit` property is specified as a single keyword chosen from the list of values below.

### Values

`contain`  
The replaced content is scaled to maintain its aspect ratio while fitting within the element’s content box. The entire object is made to fill the box, while preserving its aspect ratio, so the object will be ["letterboxed"](<https://en.wikipedia.org/wiki/Letterboxing_(filming)>) if its aspect ratio does not match the aspect ratio of the box.

`cover`  
The replaced content is sized to maintain its aspect ratio while filling the element’s entire content box. If the object's aspect ratio does not match the aspect ratio of its box, then the object will be clipped to fit.

`fill`  
The replaced content is sized to fill the element’s content box. The entire object will completely fill the box. If the object's aspect ratio does not match the aspect ratio of its box, then the object will be stretched to fit.

`none`  
The replaced content is not resized.

`scale-down`  
The content is sized as if `none` or `contain` were specified, whichever would result in a smaller concrete object size.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>fill</code></td></tr><tr class="even"><td>Applies to</td><td>replaced elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    fill | contain | cover | none | scale-down

## Examples

### Setting object-fit for an image

#### HTML

    <section>
      <h2>object-fit: fill</h2>
      <img class="fill" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <img class="fill narrow" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <h2>object-fit: contain</h2>
      <img class="contain" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <img class="contain narrow" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <h2>object-fit: cover</h2>
      <img class="cover" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <img class="cover narrow" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <h2>object-fit: none</h2>
      <img class="none" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <img class="none narrow" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <h2>object-fit: scale-down</h2>
      <img class="scale-down" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">

      <img class="scale-down narrow" src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo">
    </section>

#### CSS

    h2 {
      font-family: Courier New, monospace;
      font-size: 1em;
      margin: 1em 0 0.3em;
    }

    img {
      width: 150px;
      height: 100px;
      border: 1px solid #000;
      margin: 10px 0;
    }

    .narrow {
      width: 100px;
      height: 150px;
    }

    .fill {
      object-fit: fill;
    }

    .contain {
      object-fit: contain;
    }

    .cover {
      object-fit: cover;
    }

    .none {
      object-fit: none;
    }

    .scale-down {
      object-fit: scale-down;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#the-object-fit">CSS Images Module Level 4<br />
<span class="small">The definition of 'object-fit' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-images-3/#the-object-fit">CSS Images Module Level 3<br />
<span class="small">The definition of 'object-fit' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`object-fit`

32

79

16-79

Only supported for `<img>` elements.

36

No

19

11.6-15

10

4.4.3

32

36

19

12-14

10

2.0

## See also

- Other image-related CSS properties: [`object-position`](object-position), [`image-orientation`](image-orientation), [`image-rendering`](image-rendering), [`image-resolution`](image-resolution).
- [`background-size`](background-size)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit</a>
