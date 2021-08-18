# text-align

The `text-align` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the horizontal alignment of the content inside a block element or table-cell box. This means it works like [`vertical-align`](vertical-align) but in the horizontal direction.

## Syntax

    /* Keyword values */
    text-align: left;
    text-align: right;
    text-align: center;
    text-align: justify;
    text-align: justify-all;
    text-align: start;
    text-align: end;
    text-align: match-parent;

    /* Character-based alignment in a table column */
    text-align: ".";
    text-align: "." center;

    /* Block alignment values (Non-standard syntax) */
    text-align: -moz-center;
    text-align: -webkit-center;

    /* Global values */
    text-align: inherit;
    text-align: initial;
    text-align: unset;

The `text-align` property is specified in one of the following ways:

- Using the keyword values `start`, `end`, `left`, `right`, `center`, `justify`, `justify-all`, or `match-parent`.
- Using a `<string>` value only, in which case the other value defaults to `right`.
- Using both a keyword value and a `<string>` value.

### Values

`start` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The same as `left` if direction is left-to-right and `right` if direction is right-to-left.

`end` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The same as `right` if direction is left-to-right and `left` if direction is right-to-left.

`left`  
The inline contents are aligned to the left edge of the line box.

`right`  
The inline contents are aligned to the right edge of the line box.

`center`  
The inline contents are centered within the line box.

`justify`  
The inline contents are justified. Text should be spaced to line up its left and right edges to the left and right edges of the line box, except for the last line.

`justify-all` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Same as `justify`, but also forces the last line to be justified.

`match-parent` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Similar to `inherit`, but the values `start` and `end` are calculated according to the parent's [`direction`](direction) and are replaced by the appropriate `left` or `right` value.

[`<string>`](string) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
When applied to a table cell, specifies the alignment character around which the cell's contents will align.

## Accessibility concerns

The inconsistent spacing between words created by justified text can be problematic for people with cognitive concerns such as Dyslexia.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 | Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>start</code>, or a nameless value that acts as <code>left</code> if <a href="direction"><code>direction</code></a> is <code>ltr</code>, <code>right</code> if <a href="direction"><code>direction</code></a> is <code>rtl</code> if <code>start</code> is not supported by the browser.</td></tr><tr class="even"><td>Applies to</td><td>block containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, except for the <code>match-parent</code> value which is calculated against its parent's <code>direction</code> value and results in a computed value of either <code>left</code> or <code>right</code></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    start | end | left | right | center | justify | match-parent

## Examples

### Left alignment

#### HTML

    <p class="example">
      Integer elementum massa at nulla placerat varius.
      Suspendisse in libero risus, in interdum massa.
      Vestibulum ac leo vitae metus faucibus gravida ac in neque.
      Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
    </p>

#### CSS

    .example {
      text-align: left;
      border: solid;
    }

#### Result

### Centered text

#### HTML

    <p class="example">
      Integer elementum massa at nulla placerat varius.
      Suspendisse in libero risus, in interdum massa.
      Vestibulum ac leo vitae metus faucibus gravida ac in neque.
      Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
    </p>

#### CSS

    .example {
      text-align: center;
      border: solid;
    }

#### Result

### Justify

#### HTML

    <p class="example">
      Integer elementum massa at nulla placerat varius.
      Suspendisse in libero risus, in interdum massa.
      Vestibulum ac leo vitae metus faucibus gravida ac in neque.
      Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
    </p>

#### CSS

    .example {
      text-align: justify;
      border: solid;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#text-align">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'text-align' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>No changes</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-text-4/#alignment">CSS Text Module Level 4<br />
<span class="small">The definition of 'text-align' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Added the <code>&lt;string&gt;</code> value.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#text-align-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'text-align' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>start</code>, <code>end</code>, and <code>match-parent</code> values. Changed the unnamed initial value to <code>start</code> (which it was).</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/text.html#alignment-prop">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'text-align' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No changes</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#text-align">CSS Level 1<br />
<span class="small">The definition of 'text-align' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-align`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`block_alignment_values`

1

79

1

No

15

1.3

1

37

18

4

14

1

1

1.0

`flow_relative_values_start_and_end`

1

79

1

No

15

3.1

37

18

4

14

2

1.0

`justify-all`

No

No

No

No

No

No

No

No

No

No

No

No

`match-parent`

16

79

40

No

15

No

37

18

40

14

No

1.0

`string`

No

No

No

No

No

No

No

No

No

No

No

No

## See also

- [`margin: auto`](margin), [`margin-left: auto`](margin-left), [`vertical-align`](vertical-align)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-align" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-align</a>
