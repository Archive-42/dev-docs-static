# color-index

The `color-index` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the number of entries in the output device's color lookup table.

## Syntax

The `color-index` feature is specified as an [`<integer>`](../integer) value representing the number of entries in the output device's color lookup table. (This value is zero if the device does not use such a table.) It is a range feature, meaning that you can also use the prefixed `min-color-index` and `max-color-index` variants to query minimum and maximum values, respectively.

## Examples

### Basic example

#### HTML

    <p>This is a test.</p>

#### CSS

    p {
      color: black;
    }

    @media (color-index) {
      p {
        color: red;
      }
    }

    @media (min-color-index: 15000) {
      p {
        color: #1475ef;
      }
    }

#### Result

### Custom stylesheet

This HTML will apply a special stylesheet for devices that have at least 256 colors.

    <link rel="stylesheet" href="http://foo.bar.com/base.css" />
    <link rel="stylesheet" media="all and (min-color-index: 256)" href="http://foo.bar.com/color-stylesheet.css" />

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#color-index">Media Queries Level 4<br />
<span class="small">The definition of 'color-index' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The value can now be negative, in which case it computes to false.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#color-index">Media Queries<br />
<span class="small">The definition of 'color-index' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. The value must be nonnegative.</td></tr></tbody></table>

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

`color-index`

29

79

No

No

16

8

≤37

29

No

16

8

2.0

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-index" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-index</a>
