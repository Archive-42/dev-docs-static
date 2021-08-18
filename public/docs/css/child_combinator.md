# Child combinator

The **child combinator** (`>`) is placed between two CSS selectors. It matches only those elements matched by the second selector that are the direct children of elements matched by the first.

    /* List items that are children of the "my-things" list */
    ul.my-things > li {
      margin: 2em;
    }

Elements matched by the second selector must be the immediate children of the elements matched by the first selector. This is stricter than the [descendant combinator](descendant_combinator), which matches all elements matched by the second selector for which there exists an ancestor element matched by the first selector, regardless of the number of "hops" up the DOM.

## Syntax

    selector1 > selector2 { style properties }

## Examples

### CSS

    span {
      background-color: white;
    }

    div > span {
      background-color: DodgerBlue;
    }

### HTML

    <div>
      <span>Span #1, in the div.
        <span>Span #2, in the span that's in the div.</span>
      </span>
    </div>
    <span>Span #3, not in the div at all.</span>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#child-combinators">Selectors Level 4<br />
<span class="small">The definition of 'child combinator' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#child-combinators">Selectors Level 3<br />
<span class="small">The definition of 'child combinators' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#child-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'child selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Child_combinator`

1

12

1

7

4

1

≤37

18

4

10.1

1

1.0

## See also

- [Descendant combinator](descendant_combinator)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator</a>
