# white-space

The `white-space` CSS property sets how [white space](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace) inside an element is handled.

The property specifies two things:

- Whether and how white-space is collapsed.
- Whether lines may wrap at soft-wrap opportunities.

**Note:** To make words break _within themselves_, use [`overflow-wrap`](overflow-wrap), [`word-break`](word-break), or [`hyphens`](hyphens) instead.

## Syntax

    /* Keyword values */
    white-space: normal;
    white-space: nowrap;
    white-space: pre;
    white-space: pre-wrap;
    white-space: pre-line;
    white-space: break-spaces;

    /* Global values */
    white-space: inherit;
    white-space: initial;
    white-space: unset;

The `white-space` property is specified as a single keyword chosen from the list of values below.

### Values

`normal`  
Sequences of white space are collapsed. Newline characters in the source are handled the same as other white space. Lines are broken as necessary to fill line boxes.

`nowrap`  
Collapses white space as for `normal`, but suppresses line breaks (text wrapping) within the source.

`pre`  
Sequences of white space are preserved. Lines are only broken at newline characters in the source and at [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br) elements.

`pre-wrap`  
Sequences of white space are preserved. Lines are broken at newline characters, at [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br), and as necessary to fill line boxes.

`pre-line`  
Sequences of white space are collapsed. Lines are broken at newline characters, at [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br), and as necessary to fill line boxes.

`break-spaces`  
The behavior is identical to that of `pre-wrap`, except that:

- Any sequence of preserved white space always takes up space, including at the end of the line.
- A line breaking opportunity exists after every preserved white space character, including between white space characters.
- Such preserved spaces take up space and do not hang, and thus affect the box’s intrinsic sizes (min-content size and max-content size).

The following table summarizes the behavior of the various `white-space` values:

<table><thead><tr class="header"><th></th><th>New lines</th><th>Spaces and tabs</th><th>Text wrapping</th><th>End-of-line spaces</th><th>End-of-line other space separators</th></tr></thead><tbody><tr class="odd"><td><code>normal</code></td><td>Collapse</td><td>Collapse</td><td>Wrap</td><td>Remove</td><td>Hang</td></tr><tr class="even"><td><code>nowrap</code></td><td>Collapse</td><td>Collapse</td><td>No wrap</td><td>Remove</td><td>Hang</td></tr><tr class="odd"><td><code>pre</code></td><td>Preserve</td><td>Preserve</td><td>No wrap</td><td>Preserve</td><td>No wrap</td></tr><tr class="even"><td><code>pre-wrap</code></td><td>Preserve</td><td>Preserve</td><td>Wrap</td><td>Hang</td><td>Hang</td></tr><tr class="odd"><td><code>pre-line</code></td><td>Preserve</td><td>Collapse</td><td>Wrap</td><td>Remove</td><td>Hang</td></tr><tr class="even"><td><code>break-spaces</code></td><td>Preserve</td><td>Preserve</td><td>Wrap</td><td>Wrap</td><td>Wrap</td></tr></tbody></table>

**Notes**

There is a distinction made between **spaces** and **other space separators**. These are defined as follows:

spaces  
Spaces (U+0020), tabs (U+0009), and segment breaks (such as newlines).

other space separators  
All other space separators defined in Unicode, other than those already defined as spaces.

Where white space is said to _hang_, this can affect the size of the box when measured for intrinsic sizing.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | pre | nowrap | pre-wrap | pre-line | break-spaces

## Examples

### Basic example

    code {
      white-space: pre;
    }

### Line breaks inside &lt;pre&gt; elements

    pre {
      white-space: pre-wrap;
    }

### In action

#### HTML

    <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#propdef-white-space">CSS Text Module Level 3<br />
<span class="small">The definition of 'white-space' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Precisely defines the breaking algorithms.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/text.html#white-space-prop">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'white-space' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`white-space`

1

12

1

5.5

4

1

1

18

4

10.1

1

1.0

`break-spaces`

76

79

69

No

62

13.1

76

76

No

54

13.4

12.0

`nowrap`

1

12

1

5.5

4

1

1

18

4

10.1

1

1.0

`pre`

1

12

1

6

4

1

37

18

4

14

1

1.0

`pre-line`

1

12

3.5

8

9.5

3

37

18

4

14

1

1.0

`pre-wrap`

1

12

3

1-3.6

8

From Internet Explorer 5.5 to 7, `word-wrap: break-word;` can be used for line breaks in `pre` elements.

8

3

37

18

4

14

1

1.0

`svg_support`

No

12-79

36

10

No

No

No

No

36

No

No

No

`textarea_support`

1

12

36

5.5

4

1

37

18

36

14

1

1.0

## See also

- Properties that define how words break _within themselves_: [`overflow-wrap`](overflow-wrap), [`word-break`](word-break), [`hyphens`](hyphens)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/white-space" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/white-space</a>
