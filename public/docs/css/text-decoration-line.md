# text-decoration-line

The `text-decoration-line` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the kind of decoration that is used on text in an element, such as an underline or overline.

When setting multiple line-decoration properties at once, it may be more convenient to use the [`text-decoration`](text-decoration) shorthand property instead.

## Syntax

    /* Single keyword */
    text-decoration-line: none;
    text-decoration-line: underline;
    text-decoration-line: overline;
    text-decoration-line: line-through;
    text-decoration-line: blink;

    /* Multiple keywords */
    text-decoration-line: underline overline;               /* Two decoration lines */
    text-decoration-line: overline underline line-through;  /* Multiple decoration lines */

    /* Global values */
    text-decoration-line: inherit;
    text-decoration-line: initial;
    text-decoration-line: unset;

The `text-decoration-line` property is specified as `none`, or **one or more** space-separated values from the list below.

### Values

`none`  
Produces no text decoration.

`underline`  
Each line of text has a decorative line beneath it.

`overline`  
Each line of text has a decorative line above it.

`line-through`  
Each line of text has a decorative line going through its middle.

`blink` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
The text blinks (alternates between visible and invisible). Conforming user agents may not blink the text. This value is **deprecated** in favor of [CSS animations](animation).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | [ underline || overline || line-through || blink ] | spelling-error | grammar-error

## Examples

### Basic example

    <p class="wavy">Here's some text with wavy red underline!</p>
    <p class="both">This text has lines both above and below it.</p>

    .wavy {
      text-decoration-line: underline;
      text-decoration-style: wavy;
      text-decoration-color: red;
    }

    .both {
      text-decoration-line: underline overline;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-decoration-line-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-decoration-line' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition. The <a href="text-decoration"><code>text-decoration</code></a> property is now a shorthand to define multiple related properties.</td></tr></tbody></table>

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

`text-decoration-line`

57

79

36

6-39

No

44

12.1

8

57

57

36

6-39

43

12.2

8

7.0

`blink`

57

The `blink` value does not have any effect.

79

The `blink` value does not have any effect.

26

The `blink` value does not have any effect.

No

44

8

57

The `blink` value does not have any effect.

57

The `blink` value does not have any effect.

26

The `blink` value does not have any effect.

43

8

7.0

The `blink` value does not have any effect.

## See also

- When setting multiple line-decoration properties at once, it may be more convenient to use the [`text-decoration`](text-decoration) shorthand property instead.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line</a>
