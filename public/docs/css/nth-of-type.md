# :nth-of-type()

The `:nth-of-type()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches elements of a given type (tag name), based on their position among a group of siblings.

    /* Selects every fourth <p> element
       among any group of siblings */
    p:nth-of-type(4n) {
      color: lime;
    }

## Syntax

The `nth-of-type` pseudo-class is specified with a single argument, which represents the pattern for matching elements.

See [`:nth-child`](:nth-child) for a more detailed explanation of its syntax.

### Formal syntax

    :nth-of-type( <nth> )where
    <nth> = <an-plus-b> | even | odd

## Examples

### Basic example

#### HTML

    <div>
      <div>This element isn't counted.</div>
      <p>1st paragraph.</p>
      <p class="fancy">2nd paragraph.</p>
      <div>This element isn't counted.</div>
      <p class="fancy">3rd paragraph.</p>
      <p>4th paragraph.</p>
    </div>

#### CSS

    /* Odd paragraphs */
    p:nth-of-type(2n+1) {
      color: red;
    }

    /* Even paragraphs */
    p:nth-of-type(2n) {
      color: blue;
    }

    /* First paragraph */
    p:nth-of-type(1) {
      font-weight: bold;
    }

    /* This will match the 3rd paragraph as it will match elements which are 2n+1 AND have a class of fancy.
    The second paragraph has a class of fancy but is not matched as it is not :nth-of-type(2n+1) */
    p.fancy:nth-of-type(2n+1) {
      text-decoration: underline;
    }

#### Result

**Note**

There is no way to select the nth-of-class using this selector. The selector looks at the type only when creating the list of matches. You can however apply CSS to an element based on `:nth-of-type` location **and** a class, as shown in the example above.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#nth-of-type-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':nth-of-type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Matching elements are not required to have a parent.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#nth-of-type-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':nth-of-type' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:nth-of-type`

1

12

Before Edge 16, Microsoft Edge treats all unknown elements (such as custom elements) as the same element type.

3.5

9

Internet Explorer treats all unknown elements (such as custom elements) as the same element type.

9.5

3.1

2

18

4

10.1

3.1

1.0

## See also

- [`:nth-child`](:nth-child), [`:nth-last-of-type`](:nth-last-of-type)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-of-type</a>
