# text-decoration-style

The `text-decoration-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the style of the lines specified by [`text-decoration-line`](text-decoration-line). The style applies to all lines that are set with `text-decoration-line`.

If the specified decoration has a specific semantic meaning, like a line-through line meaning that some text has been deleted, authors are encouraged to denote this meaning using an HTML tag, like [`<del>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del) or [`<s>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/s). As browsers can disable styling in some cases, the semantic meaning won't disappear in such a situation.

When setting multiple line-decoration properties at once, it may be more convenient to use the [`text-decoration`](text-decoration) shorthand property instead.

## Syntax

    /* Keyword values */
    text-decoration-style: solid;
    text-decoration-style: double;
    text-decoration-style: dotted;
    text-decoration-style: dashed;
    text-decoration-style: wavy;

    /* Global values */
    text-decoration-style: inherit;
    text-decoration-style: initial;
    text-decoration-style: unset;

### Values

solid  
Draws a single line.

double  
Draws a double line.

dotted  
Draws a dotted line.

dashed  
Draws a dashed line.

wavy  
Draws a wavy line.

-moz-none<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Draws no line. Use [`text-decoration-line`](text-decoration-line)`: none` instead.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>solid</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    solid | double | dotted | dashed | wavy

## Examples

### Setting a wavy underline

    .example {
           -moz-text-decoration-line: underline;
           -moz-text-decoration-style: wavy;
           -moz-text-decoration-color: red;
        -webkit-text-decoration-line: underline;
        -webkit-text-decoration-style: wavy;
        -webkit-text-decoration-color: red;
    }

#### CSS

    .wavy {
      text-decoration-line: underline;
      text-decoration-style: wavy;
      text-decoration-color: red;
    }

#### HTML

    <p class="wavy">This text has a wavy red line beneath it.</p>

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-decoration-style-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-decoration-style' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition. The <a href="text-decoration"><code>text-decoration</code></a> property is now a shorthand to define multiple related properties.</td></tr></tbody></table>

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

`text-decoration-style`

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

`wavy`

57

79

6

No

44

8

57

57

6

43

8

7.0

## See also

- When setting multiple line-decoration properties at once, it may be more convenient to use the [`text-decoration`](text-decoration) shorthand property instead.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style</a>
