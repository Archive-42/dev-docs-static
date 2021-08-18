# aspect-ratio

The `aspect-ratio` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the aspect ratio of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).

## Syntax

The `aspect-ratio` feature is specified as a [`<ratio>`](../ratio) value representing the width-to-height aspect ratio of the viewport. It is a range feature, meaning you can also use the prefixed `min-aspect-ratio` and `max-aspect-ratio` variants to query minimum and maximum values, respectively.

## Examples

The example below is contained in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), which creates its own viewport. Resize the `<iframe>` to see `aspect-ratio` in action.

Note that, when none of the media query conditions are true, the background will turn white because none of the below rules will be applied to the `<div>` inside the `<iframe>`. See if you can find which width and height values trigger this!

### HTML

    <div id='inner'>
      Watch this element as you resize your viewport's width and height.
    </div>

### CSS

    /* Minimum aspect ratio */
    @media (min-aspect-ratio: 8/5) {
      div {
        background: #9af; /* blue */
      }
    }

    /* Maximum aspect ratio */
    @media (max-aspect-ratio: 3/2) {
      div {
        background: #9ff;  /* cyan */
      }
    }

    /* Exact aspect ratio, put it at the bottom to avoid override*/
    @media (aspect-ratio: 1/1) {
      div {
        background: #f9a; /* red */
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#aspect-ratio">Media Queries Level 4<br />
<span class="small">The definition of 'aspect-ratio' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#aspect-ratio">Media Queries<br />
<span class="small">The definition of 'aspect-ratio' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`aspect-ratio`

3

12

3.5

9

10

5

≤37

18

4

10.1

4.2

1.0

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/aspect-ratio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/aspect-ratio</a>
