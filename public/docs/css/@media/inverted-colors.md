# inverted-colors

The `inverted-colors` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test whether the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) or underlying OS is inverting colors.

## Syntax

The `inverted-colors` feature is specified as a keyword value chosen from the list below.

`none`  
Colors are displayed normally.

`inverted`  
All pixels within the displayed area have been inverted.

## Examples

### HTML

    <p>If you're using inverted colors, this text should be blue on white (the inverse of yellow on black). If you're not, it should be red on light gray.</p>
    <p>If the text is gray, your browser doesn't support the `inverted-colors` media feature.</p>

### CSS

    p {
      color: gray;
    }

    @media (inverted-colors: inverted) {
      p {
        background: black;
        color: yellow;
      }
    }

    @media (inverted-colors: none) {
      p {
        background: #eee;
        color: red;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/#inverted">Media Queries Level 5<br />
<span class="small">The definition of 'inverted-colors' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

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

`inverted-colors`

No

No

No

No

No

9.1

No

No

No

No

10

No

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/inverted-colors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/inverted-colors</a>
