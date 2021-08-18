# :last-of-type

The `:last-of-type` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents the last element of its type among a group of sibling elements.

    /* Selects any <p> that is the last element
       of its type among its siblings */
    p:last-of-type {
      color: lime;
    }

**Note**: As originally defined, the selected element had to have a parent. Beginning with Selectors Level 4, this is no longer required.

## Syntax

    :last-of-type

## Examples

### Styling the last paragraph

#### HTML

    <h2>Heading</h2>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>

#### CSS

    p:last-of-type {
      color: red;
      font-style: italic;
    }

#### Result

### Nested elements

This example shows how nested elements can also be targeted. Note that the [universal selector](universal_selectors) (`*`) is implied when no simple selector is written.

#### HTML

    <article>
      <div>This `div` is first.</div>
      <div>This <span>nested `span` is last</span>!</div>
      <div>This <em>nested `em` is first</em>, but this <em>nested `em` is last</em>!</div>
      <b>This `b` qualifies!</b>
      <div>This is the final `div`!</div>
    </article>

#### CSS

    article :last-of-type {
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#last-of-type-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':last-of-type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#last-of-type-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':last-of-type' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:last-of-type`

1

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

- [`:last-child`](:last-child), [`:nth-last-of-type`](:nth-last-of-type)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type</a>
