# text-underline-position

The `text-underline-position` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the position of the underline which is set using the [`text-decoration`](text-decoration) property's `underline` value.

## Syntax

    /* Single keyword */
    text-underline-position: auto;
    text-underline-position: under;
    text-underline-position: left;
    text-underline-position: right;

    /* Multiple keywords */
    text-underline-position: under left;
    text-underline-position: right under;

    /* Global values */
    text-underline-position: inherit;
    text-underline-position: initial;
    text-underline-position: unset;

## Syntax

### Values

`auto`  
The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) uses its own algorithm to place the line at or under the alphabetic baseline.

`from-font`  
If the font file includes information about a preferred position, use that value. If the font file doesn't include this information, behave as if `auto` was set, with the browser choosing an appropriate position.

`under`  
Forces the line to be set below the alphabetic baseline, at a position where it won't cross any descenders. This is useful for ensuring legibility with chemical and mathematical formulas, which make a large use of subscripts.

`left`  
In vertical writing-modes, this keyword forces the line to be placed on the _left_ side of the text. In horizontal writing-modes, it is a synonym of `under`.

`right`  
In vertical writing-modes, this keyword forces the line to be placed on the _right_ side of the text. In horizontal writing-modes, it is a synonym of `under`.

`auto-pos` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
A synonym of `auto`, which should be used instead.

`above` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Forces the line to be above the text. When used with East-Asian text, using the `auto` keyword will lead to a similar effect.

`below` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Forces the line to be below the text. When used with alphabetic text, using the `auto` keyword will lead to a similar effect.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | from-font | [ under || [ left | right ] ]

## Examples

### A simple example

Let's take a couple of simple example paragraphs:

    <p class="horizontal">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Nullam consectetur ac turpis vel laoreet. Nullam volutpat pharetra lorem, sit
    amet feugiat tortor volutpat quis. Nam eget sodales quam. Aliquam accumsan
    tellus ac erat posuere.</p>

    <p class="vertical">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Nullam consectetur ac turpis vel laoreet. Nullam volutpat pharetra lorem, sit
    amet feugiat tortor volutpat quis. Nam eget sodales quam. Aliquam accumsan
    tellus ac erat posuere.</p>

Our CSS looks like this:

    p {
      font-size: 1.5rem;
      text-transform: capitalize;
      text-decoration: underline;
      text-decoration-thickness: 2px;
    }

    .horizontal {
      text-underline-position: under;
    }

    .vertical {
      writing-mode: vertical-rl;
      text-underline-position: left;
    }

In this example we set both the paragraphs to have a thick underline. In the horizontal text we use `text-underline-position: under;` to put the underline below all the descenders.

In the text with a vertical `writing-mode` set, we can then use values of `left` or `right` to make the underline appear on the left or right of the text as required.

The live example looks like this:

### Setting text-underline-position globally

Because the `text-underline-position` property inherits and is not reset by the [`text-decoration`](text-decoration) shorthand property, it may be appropriate to set its value at a global level. For example, the `under` value may be appropriate for a document with lots of chemical and mathematical formulas, which make a large use of subscripts.

    :root {
      text-underline-position: under;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-underline-position-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-underline-position' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-underline-position`

33

12

74

6

20

12.1

9

4.4.3

33

No

20

No

2.0

`above_below`

No

12-79

74

6

No

No

No

No

No

No

No

No

`auto-pos`

No

12-79

No

6

No

No

No

No

No

No

No

No

`from-font`

87

87

74

No

No

No

87

87

No

No

No

No

`left_right`

71

79

74

No

58

No

71

71

No

50

No

10.0

`under`

33

79

74

No

20

12.1

4.4.3

33

No

20

No

2.0

## See also

- The [`text-decoration`](text-decoration) property is a shorthand for setting most text-decoration properties, including [`text-decoration-line`](text-decoration-line), [`text-decoration-color`](text-decoration-color), and [`text-decoration-style`](text-decoration-style). However, it does not set `text-underline-position`.
- Microsoft [non-standard values documentation](https://msdn.microsoft.com/en-us/library/ie/ms531176%28v=vs.85%29.aspx)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-position</a>
