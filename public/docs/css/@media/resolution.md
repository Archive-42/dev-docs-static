# resolution

The `resolution` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the pixel density of the output device.

## Syntax

The `resolution` feature is specified as a [`<resolution>`](../resolution) value representing the pixel density of the output device. It is a range feature, meaning that you can also use the prefixed `min-resolution` and `max-resolution` variants to query minimum and maximum values, respectively.

## Examples

### HTML

    <p>This is a test of your device's pixel density.</p>

### CSS

    /* Exact resolution */
    @media (resolution: 150dpi) {
      p {
        color: red;
      }
    }

    /* Minimum resolution */
    @media (min-resolution: 72dpi) {
      p {
        text-decoration: underline;
      }
    }

    /* Maximum resolution */
    @media (max-resolution: 300dpi) {
      p {
        background: yellow;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-3/#resolution">Media Queries<br />
<span class="small">The definition of 'resolution' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`resolution`

29

12

8

3.5

Supports [`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values only.

9

16

10-15

No

See [bug 78087](https://webkit.org/b/78087).

≤37

29

8

4

Supports [`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values only.

16

10.1-14

No

See [bug 78087](https://webkit.org/b/78087).

2.0

## See also

- [`window.devicePixelRatio`](https://developer.mozilla.org/en-US/docs/Web/API/Window/devicePixelRatio)
- The [`image-resolution`](../image-resolution) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/resolution" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/resolution</a>
