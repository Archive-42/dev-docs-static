# :nth-last-of-type()

The `:nth-last-of-type()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches elements of a given type, based on their position among a group of siblings, counting from the end.

    /* Selects every fourth <p> element
       among any group of siblings,
       counting backwards from the last one */
    p:nth-last-of-type(4n) {
      color: lime;
    }

**Note:** This pseudo-class is essentially the same as [`:nth-of-type`](:nth-of-type), except it counts items backwards from the _end_, not forwards from the beginning.

## Syntax

The `nth-last-of-type` pseudo-class is specified with a single argument, which represents the pattern for matching elements, counting from the end.

See [`:nth-last-child`](:nth-last-child) for a more detailed explanation of its syntax.

### Formal syntax

    :nth-last-of-type( <nth> )where
    <nth> = <an-plus-b> | even | odd

## Examples

### HTML

    <div>
      <span>This is a span.</span>
      <span>This is another span.</span>
      <em>This is emphasized.</em>
      <span>Wow, this span gets limed!!!</span>
      <strike>This is struck through.</strike>
      <span>Here is one last span.</span>
    </div>

### CSS

    span:nth-last-of-type(2) {
      background-color: lime;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#nth-last-of-type-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':nth-last-of-type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#nth-last-of-type-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':nth-last-of-type' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:nth-last-of-type`

4

12

Before Edge 16, Microsoft Edge treats all unknown elements (such as custom elements) as the same element type.

3.5

9

Internet Explorer treats all unknown elements (such as custom elements) as the same element type.

9.5

3.2

2

18

4

10.1

3.2

1.0

## See also

- [`:nth-last-child`](:nth-last-child), [`:nth-of-type`](:nth-of-type)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-of-type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-of-type</a>
