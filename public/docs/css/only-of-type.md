# :only-of-type

The `:only-of-type` CSS [pseudo-class](pseudo-classes) represents an element that has no siblings of the same type.

    /* Selects each <p>, but only if it is the */
    /* only <p> element inside its parent */
    p:only-of-type {
      background-color: lime;
    }

**Note**: As originally defined, the selected element had to have a parent. Beginning with Selectors Level 4, this is no longer required.

## Syntax

    :only-of-type

## Examples

### Styling elements with no siblings of the same type

#### HTML

    <main>
      <div>I am `div` #1.</div>
      <p>I am the only `p` among my siblings.</p>
      <div>I am `div` #2.</div>
      <div>I am `div` #3.
        <i>I am the only `i` child.</i>
        <em>I am `em` #1.</em>
        <em>I am `em` #2.</em>
      </div>
    </main>

#### CSS

    main :only-of-type {
      color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#only-of-type-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':only-of-type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#only-of-type-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':only-of-type' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:only-of-type`

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

- [`:only-child`](:only-child)
- [`:first-of-type`](:first-of-type)
- [`:last-of-type`](:last-of-type)
- [`:nth-of-type`](:nth-of-type)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type</a>
