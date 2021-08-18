# overflow-wrap

The `overflow-wrap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies to inline elements, setting whether the browser should insert line breaks within an otherwise unbreakable string to prevent text from overflowing its line box.

**Note:** In contrast to [`word-break`](word-break), `overflow-wrap` will only create a break if an entire word cannot be placed on its own line without overflowing.

The property was originally a nonstandard and unprefixed Microsoft extension called `word-wrap`, and was implemented by most browsers with the same name. It has since been renamed to `overflow-wrap`, with `word-wrap` being an alias.

## Syntax

    /* Keyword values */
    overflow-wrap: normal;
    overflow-wrap: break-word;
    overflow-wrap: anywhere;

    /* Global values */
    overflow-wrap: inherit;
    overflow-wrap: initial;
    overflow-wrap: unset;

The `overflow-wrap` property is specified as a single keyword chosen from the list of values below.

### Values

`normal`  
Lines may only break at normal word break points (such as a space between two words).

`anywhere`  
To prevent overflow, an otherwise unbreakable string of characters — like a long word or URL — may be broken at any point if there are no otherwise-acceptable break points in the line. No hyphenation character is inserted at the break point. Soft wrap opportunities introduced by the word break are considered when calculating min-content intrinsic sizes.

`break-word`  
The same as the `anywhere` value, with normally unbreakable words allowed to be broken at arbitrary points if there are no otherwise acceptable break points in the line, but soft wrap opportunities introduced by the word break are NOT considered when calculating min-content intrinsic sizes.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>non-replaced inline elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | break-word | anywhere

## Examples

### Comparing overflow-wrap, word-break, and hyphens

This example compares the results of `overflow-wrap`, `word-break`, and `hyphens` when breaking up a long word.

#### HTML

    <p>They say the fishing is excellent at
      Lake <em class="normal">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
      though I've never been there myself. (<code>normal</code>)</p>
    <p>They say the fishing is excellent at
      Lake <em class="ow-anywhere">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
      though I've never been there myself. (<code>overflow-wrap: anywhere</code>)</p>
    <p>They say the fishing is excellent at
      Lake <em class="ow-break-word">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
      though I've never been there myself. (<code>overflow-wrap: break-word</code>)</p>
    <p>They say the fishing is excellent at
      Lake <em class="word-break">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
      though I've never been there myself. (<code>word-break</code>)</p>
    <p>They say the fishing is excellent at
      Lake <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
      though I've never been there myself. (<code>hyphens</code>, without <code>lang</code> attribute)</p>
    <p lang="en">They say the fishing is excellent at
      Lake <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
      though I've never been there myself. (<code>hyphens</code>, English rules)</p>
    <p class="hyphens" lang="de">They say the fishing is excellent at
      Lake <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
      though I've never been there myself. (<code>hyphens</code>, German rules)</p>

#### CSS

    p {
       width: 13em;
       margin: 2px;
       background: gold;
    }

    .ow-anywhere {
       overflow-wrap: anywhere;
    }

    .ow-break-word {
       overflow-wrap: break-word;
    }

    .word-break {
       word-break: break-all;
    }

    .hyphens {
       hyphens: auto;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#propdef-overflow-wrap">CSS Text Module Level 3<br />
<span class="small">The definition of 'overflow-wrap' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>non-replaced inline elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

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

`overflow-wrap`

23

1

18

12

49

3.5

5.5

12.1

10.5

6.1

1

4.4

1

25

18

49

4

12.1

11

7

1

1.5

1.0

`anywhere`

80

80

65

No

67

No

80

80

65

No

No

13.0

`break-word`

1

12

3.5

5.5

10.5

1

≤37

18

4

11

1

1.0

## See also

- [`word-break`](word-break)
- [`hyphens`](hyphens)
- [`text-overflow`](text-overflow)
- [Guide to wrapping and breaking text](css_text/wrapping_text)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap</a>
