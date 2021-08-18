# General sibling combinator

The **general sibling combinator** (`~`) separates two selectors and matches _all iterations_ of the second element, that are following the first element (though not necessarily immediately), and are children of the same parent [element](https://developer.mozilla.org/en-US/docs/Glossary/Element).

    /* Paragraphs that are siblings of and
       subsequent to any image */
    img ~ p {
      color: red;
    }

## Syntax

    former_element ~ target_element { style properties }

## Examples

### CSS

    p ~ span {
      color: red;
    }

### HTML

    <span>This is not red.</span>
    <p>Here is a paragraph.</p>
    <code>Here is some code.</code>
    <span>And here is a red span!</span>
    <span>And this is a red span!</span>
    <code>More code...</code>
    <div> How are you? </div>
    <p> Whatever it may be, keep smiling. </p>
    <h1> Dream big </h1>
    <h2> that's all. </h2>
    <span>And yet again this is a red span!</span>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#general-sibling-combinators">Selectors Level 4<br />
<span class="small">The definition of 'subsequent-sibling combinator' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Renames it the "subsequent-sibling" combinator.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#general-sibling-combinators">Selectors Level 3<br />
<span class="small">The definition of 'general sibling combinator' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`General_sibling_combinator`

1

12

1

7

9

3

≤37

18

4

14

1

1.0

## See also

- [Adjacent sibling combinator](adjacent_sibling_combinator)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_combinator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_combinator</a>
