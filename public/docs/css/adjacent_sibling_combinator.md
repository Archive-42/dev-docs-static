# Adjacent sibling combinator

The **adjacent sibling combinator** (`+`) separates two selectors and matches the second element only if it _immediately_ follows the first element, and both are children of the same parent [`element`](https://developer.mozilla.org/en-US/docs/Web/API/Element).

    /* Paragraphs that come immediately after any image */
    img + p {
      font-weight: bold;
    }

## Syntax

    former_element + target_element { style properties }

## Examples

### CSS

    li:first-of-type + li {
      color: red;
    }

### HTML

    <ul>
      <li>One</li>
      <li>Two!</li>
      <li>Three</li>
    </ul>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#adjacent-sibling-combinators">Selectors Level 4<br />
<span class="small">The definition of 'next-sibling combinator' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Renames it the "next-sibling" combinator.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#adjacent-sibling-combinators">Selectors Level 3<br />
<span class="small">The definition of 'Adjacent sibling combinator' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#adjacent-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'Adjacent sibling selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Adjacent_sibling_combinator`

1

12

1

7

\["Internet Explorer 7 doesn't update the style correctly when an element is dynamically placed before an element that matched the selector.", "In Internet Explorer 8, if an element is inserted dynamically by clicking on a link the first-child style isn't applied until the link loses focus."\]

3.5

1

≤37

18

4

10.1

1

1.0

## See also

- [General sibling combinator](general_sibling_combinator)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Adjacent_sibling_combinator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Adjacent_sibling_combinator</a>
