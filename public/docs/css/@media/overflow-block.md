# overflow-block

The `overflow-block` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test how the output device handles content that overflows the initial [containing block](../containing_block) along the block axis.

## Syntax

The `overflow-block` feature is specified as a keyword value chosen from the list below.

`none`  
Content that overflows the block axis is not displayed.

`scroll`  
Content that overflows the block axis can be seen by scrolling to it.

`optional-paged`  
Content that overflows the block axis can be seen by scrolling to it, but page breaks can be manually triggered (such as via [`break-inside`](../break-inside), etc.) to cause the following content to display on the following page.

`paged`  
Content is broken up into discrete pages; content that overflows one page in the block axis is displayed on the following page.

## Examples

### HTML

    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam ac turpis eleifend, fringilla velit ac, aliquam tellus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nunc velit erat, tempus id rutrum sed, dapibus ut urna. Integer vehicula nibh a justo imperdiet rutrum. Nam faucibus pretium orci imperdiet sollicitudin. Nunc id facilisis dui. Proin elementum et massa et feugiat. Integer rutrum ullamcorper eleifend. Proin sit amet tincidunt risus. Sed nec augue congue eros accumsan tincidunt sed eget ex.</p>

### CSS

    @media (overflow-block: scroll) {
      p {
        color: red;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#mf-overflow-block">Media Queries Level 4<br />
<span class="small">The definition of 'overflow-block' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`overflow-block`

No

No

66

No

No

No

No

No

66

No

No

No

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/overflow-block" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/overflow-block</a>
