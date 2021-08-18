# hover

The `hover` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test whether the user's _primary_ input mechanism can hover over elements.

## Syntax

The `hover` feature is specified as a keyword value chosen from the list below.

`none`  
The primary input mechanism cannot hover at all or cannot conveniently hover (e.g., many mobile devices emulate hovering when the user performs an inconvenient long tap), or there is no primary pointing input mechanism.

`hover`  
The primary input mechanism can conveniently hover over elements.

## Examples

### HTML

    <a href="#">Try hovering over me!</a>

### CSS

    @media (hover: hover) {
      a:hover {
        background: yellow;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#hover">Media Queries Level 4<br />
<span class="small">The definition of 'hover' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`hover`

38

Before Chrome 41, the implementation was buggy and reported `(hover: none)` on non-touch-based computers with a mouse/trackpad. See [bug 441613](https://crbug.com/441613).

12

64

No

28

9

38

Before Chrome 41, the implementation was buggy and reported `(hover: none)` on non-touch-based computers with a mouse/trackpad. See [bug 441613](https://crbug.com/441613).

50

64

28

9

5.0

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/hover" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/hover</a>
