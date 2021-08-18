# color

The `color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the number of bits per color component (red, green, blue) of the output device.

## Syntax

The `color` feature is specified as an [`<integer>`](../integer) value that represents the number of bits per color component (red, green, blue) of the output device. If the device is not a color device, the value is zero. It is a range feature, meaning that you can also use the prefixed `min-color` and `max-color` variants to query minimum and maximum values, respectively.

**Note:** If the various color components are represented by different numbers of bits, the smallest number is used. For example, if a display uses 5 bits for blue and red and 6 bits for green, then the device is considered to use 5 bits per color component. If the device uses indexed colors, the minimum number of bits per color component in the color table is used.

See [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color) to learn more about using CSS to apply color to HTML.

## Examples

### HTML

    <p>This text should be black on non-color devices, red on devices with a low number of colors, and greenish on devices with a high number of colors.</p>

### CSS

    p {
      color: black;
    }

    /* Any color device */
    @media (color) {
      p {
        color: red;
      }
    }

    /* Any color device with at least 8 bits per color component */
    @media (min-color: 8) {
      p {
        color: #24ba13;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#color">Media Queries Level 4<br />
<span class="small">The definition of 'color' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The value can now be negative, in which case it computes to false.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#color">Media Queries<br />
<span class="small">The definition of 'color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. The value must be nonnegative.</td></tr></tbody></table>

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

`color`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

## See also

- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)
- The CSS [`color`](../color) property
- The CSS [`<color>`](../color_value) data unit

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color</a>
