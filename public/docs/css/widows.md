# widows

The `widows` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the minimum number of lines in a block container that must be shown at the _top_ of a [page](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media), region, or [column](css_columns).

    /* <integer> values */
    widows: 2;
    widows: 3;

    /* Global values */
    widows: inherit;
    widows: initial;
    widows: unset;

In typography, a _widow_ is the last line of a paragraph that appears alone at the top of a page. (The paragraph is continued from a prior page.)

## Syntax

### Values

[`<integer>`](integer)  
The minimum number of lines that can stay by themselves at the top of a new fragment after a fragmentation break. The value must be positive.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>2</code></td></tr><tr class="even"><td>Applies to</td><td>block container elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <integer>

## Examples

### Controlling column widows

#### HTML

    <div>
      <p>This is the first paragraph containing some text.</p>
      <p>This is the second paragraph containing some more text than the first one. It is used to demonstrate how widows work.</p>
      <p>This is the third paragraph. It has a little bit more text than the first one.</p>
    </div>

#### CSS

    div {
      background-color: #8cffa0;
      columns: 3;
      widows: 2;
    }

    p {
      background-color: #8ca0ff;
    }

    p:first-child {
      margin-top: 0;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-break-3/#widows-orphans">CSS Fragmentation Module Level 3<br />
<span class="small">The definition of 'widows' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extends <code>widows</code> to apply to any type of fragment, including pages, regions, or columns.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-multicol-1/#filling-columns">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'widows' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Recommendations to consider <code>widows</code> in relation to columns.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/page.html#break-inside">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'widows' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`widows`

25

12

No

8

9.2

1.3

≤37

25

No

14

1

1.5

## See also

- [`orphans`](orphans)
- [Paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/widows" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/widows</a>
