# any-hover

The `any-hover` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test whether _any_ available input mechanism can hover over elements.

## Syntax

The `any-hover` feature is specified as a keyword value chosen from the list below.

`none`  
None of the available input mechanism(s) can hover conveniently, or there is no pointing input mechanism.

`hover`  
One or more available input mechanisms can conveniently hover over elements.

## Examples

### Testing whether input methods can hover

#### HTML

    <a href="#">Try hovering over me!</a>

#### CSS

    @media (any-hover: hover) {
      a:hover {
        background: yellow;
      }
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#descdef-media-any-hover">Media Queries Level 4<br />
<span class="small">The definition of 'any-hover' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`any-hover`

41

16

64

No

28

9

41

41

64

28

9

5.0

## See also

- [the `hover` media feature](hover)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-hover" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-hover</a>
