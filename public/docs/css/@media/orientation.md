# orientation

The `orientation` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the orientation of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) (or the page box, for [paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media)).

**Note:** This feature does not correspond to _device_ orientation. Opening the soft keyboard on many devices in portrait orientation will cause the viewport to become wider than it is tall, thereby causing the browser to use landscape styles instead of portrait.

## Syntax

The `orientation` feature is specified as a keyword value chosen from the list below.

### Keyword values

`portrait`  
The viewport is in a portrait orientation, i.e., the height is greater than or equal to the width.

`landscape`  
The viewport is in a landscape orientation, i.e., the width is greater than the height.

## Examples

### HTML

    <div>Box 1</div>
    <div>Box 2</div>
    <div>Box 3</div>

### CSS

    body {
      display: flex;
    }

    div {
      background: yellow;
    }

    @media (orientation: landscape) {
      body {
        flex-direction: row;
      }
    }

    @media (orientation: portrait) {
      body {
        flex-direction: column;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#orientation">Media Queries Level 4<br />
<span class="small">The definition of 'orientation' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#orientation">Media Queries<br />
<span class="small">The definition of 'orientation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`orientation`

3

12

2

9

10.6

5

≤37

18

4

11

4.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/orientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/orientation</a>
