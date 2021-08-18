# width

The `width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the width of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) (or the page box, for [paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media)).

## Syntax

The `width` feature is specified as a [`<length>`](../length) value representing the viewport width. It is a range feature, meaning that you can also use the prefixed `min-width` and `max-width` variants to query minimum and maximum values, respectively.

## Examples

### HTML

    <div>Watch this element as you resize your viewport's width.</div>

### CSS

    /* Exact width */
    @media (width: 360px) {
      div {
        color: red;
      }
    }

    /* Minimum width */
    @media (min-width: 35rem) {
      div {
        background: yellow;
      }
    }

    /* Maximum width */
    @media (max-width: 50rem) {
      div {
        border: 2px solid blue;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#width">Media Queries Level 4<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The value can now be negative, in which case it computes to false.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#width">Media Queries<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. The value must be nonnegative.</td></tr></tbody></table>

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

`width`

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

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/width</a>
