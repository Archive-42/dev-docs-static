# image-orientation

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `image-orientation` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies a layout-independent correction to the orientation of an image. It should _not_ be used for any other orientation adjustments; instead, the [`transform`](transform) property should be used with the `rotate` [`<transform-function>`](transform-function).

**Warning:** This property is deprecated in the specification. Its functionality may be moved into properties on the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) and/or [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) elements, with the possible exception of `from-image`. The `flip` and `<angle>` values were made obsolete in Firefox 63.

    /* keyword values */
    image-orientation: none;
    image-orientation: from-image; /* Use EXIF data from the image */

    /* Global values */
    image-orientation: inherit;
    image-orientation: initial;
    image-orientation: unset;

    /* Obsolete Values.
        This deprecated API should no longer be used, but will probably still work.

     */
    image-orientation: 90deg; /* Rotate 90deg */
    image-orientation: 90deg flip; /* Rotate 90deg, and flip it horizontally */
    image-orientation: flip; /* No rotation, only applies a horizontal flip */

## Syntax

### Values

`none`  
Does not apply any additional image rotation; the image is oriented as encoded or as other CSS property values dictate.

`from-image`  
Default initial value. The [EXIF](https://en.wikipedia.org/wiki/EXIF) information contained in the image is used to rotate the image appropriately.

[`<angle>`](angle) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
The [`<angle>`](angle) of rotation to apply to the image. It is rounded to the nearest `90deg` (`0.25turn`).

`flip` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
The image is flipped horizontally (i.e., reflected) after the rotation given by the [`<angle>`](angle) value is applied. If no [`<angle>`](angle) is given, `0deg` is used.

## Description

This property is intended _only_ to be used for the purpose of correcting the orientation of images which were shot with the camera rotated. It should _not_ be used for arbitrary rotations. For any purpose other than correcting an image's orientation due to how it was shot or scanned, use a [`transform`](transform) property with the `rotate` keyword to specify rotation. This includes any user-directed changes to the orientation of the image, or changes required for printing in portrait versus landscape orientation.

If used in conjunction with other CSS properties, such as a [`<transform-function>`](transform-function), any `image-orientation` rotation is applied before any other transformations.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>from-image</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>an <a href="angle"><code>&lt;angle&gt;</code></a>, rounded to the next quarter turn from <code>0deg</code> and normalized, that is moduloing the value by <code>1turn</code></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    from-image | <angle> | [ <angle>? flip ]

## Examples

### Orienting image from image data

#### CSS

    #image {
      image-orientation: from-image; /* Can be changed in the live sample */
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-3/#the-image-orientation">CSS Images Module Level 3<br />
<span class="small">The definition of 'image-orientation' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`image-orientation`

81

81

26

No

67

13.1

81

81

26

No

13.4

13.0

`flip_and_angle`

No

No

26-63

No

No

No

No

No

26-63

No

No

No

## See also

- Other image-related CSS properties: [`object-fit`](object-fit), [`object-position`](object-position), [`image-orientation`](image-orientation), [`image-rendering`](image-rendering), [`image-resolution`](image-resolution).
- [`transform`](transform) and [`rotate`](rotate)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/image-orientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/image-orientation</a>
