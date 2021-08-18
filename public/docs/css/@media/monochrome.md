# monochrome

The `monochrome` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the number of bits per pixel in the monochrome frame buffer of the output device.

## Syntax

The `monochrome` feature is specified as an [`<integer>`](../integer) representing the number of bits per pixel in the monochrome frame buffer. If the device is not a monochrome device, the value is zero. It is a range feature, meaning that you can also use the prefixed `min-monochrome` and `max-monochrome` variants to query minimum and maximum values, respectively.

## Examples

### HTML

    <p class="mono">Your device supports monochrome pixels!</p>
    <p class="no-mono">Your device doesn't support monochrome pixels.</p>

### CSS

    p {
      display: none;
    }

    /* Any monochrome device */
    @media (monochrome) {
      p.mono {
        display: block;
        color: #333;
      }
    }

    /* Any non-monochrome device */
    @media (monochrome: 0) {
      p.no-mono {
        display: block;
        color: #ee3636;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#monochrome">Media Queries Level 4<br />
<span class="small">The definition of 'monochrome' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The value can now be negative, in which case it computes to false.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#monochrome">Media Queries<br />
<span class="small">The definition of 'monochrome' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. The value must be nonnegative.</td></tr></tbody></table>

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

`monochrome`

1

79

2

No

10

3

≤37

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/monochrome" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/monochrome</a>
