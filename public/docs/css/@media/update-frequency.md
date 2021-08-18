# update

The `update` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test how frequently (if at all) the output device is able to modify the appearance of content.

## Syntax

The `update` feature is specified as a single keyword value chosen from the list below.

`none`  
Once it has been rendered, the layout can no longer be updated. Example: documents printed on paper.

`slow`  
The layout may change dynamically according to the usual rules of CSS, but the output device is not able to render or display changes quickly enough for them to be perceived as a smooth animation. Examples: e-book readers or severely underpowered devices.

`fast`  
The layout may change dynamically according to the usual rules of CSS, and the output device is not unusually constrained in speed, so regularly-updating things like [CSS Animations](../css_animations) can be used. Example: computer screens.

## Examples

### HTML

    <p>If this text animates for you, you are using a fast-updating device.</p>

### CSS

    @keyframes jiggle {
      from {
        transform: translateY(0);
      }

      to {
        transform: translateY(25px);
      }
    }

    @media (update: fast) {
      p {
        animation: 1s jiggle linear alternate infinite;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#update">Media Queries Level 4<br />
<span class="small">The definition of 'update' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`update-frequency`

No

No

No

No

No

No

No

No

No

No

No

No

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/update-frequency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/update-frequency</a>
