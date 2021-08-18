# text-justify

The `text-justify` CSS property sets what type of justification should be applied to text when [`text-align`](text-align)`: justify;` is set on an element.

    text-justify: none;
    text-justify: auto;
    text-justify: inter-word;
    text-justify: inter-character;
    text-justify: distribute; /* Deprecated value */

## Syntax

The `text-justify` property is specified as a single keyword chosen from the list of values below.

### Values

`none`  
The text justification is turned off. This has the same effect as not setting [`text-align`](text-align) at all, although it is useful if you need to turn justification on and off for some reason.

`auto`  
The browser chooses the best type of justification for the current situation based on a balance between performance and quality, but also on what is most appropriate for the language of the text (e.g., English, CJK languages, etc.). This is the default justification used if `text-justify` is not set at all.

`inter-word`  
The text is justified by adding space between words (effectively varying [`word-spacing`](word-spacing)), which is most appropriate for languages that separate words using spaces, like English or Korean.

`inter-character`  
The text is justified by adding space between characters (effectively varying [`letter-spacing`](letter-spacing)), which is most appropriate for languages like Japanese.

`distribute` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Exhibits the same behavior as `inter-character`; this value is kept for backwards compatibility.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>inline-level and table-cell elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | inter-character | inter-word | none

## Examples

### Demonstration of the different values of text-justify

    p {
      font-size: 1.5em;
      border: 1px solid black;
      padding: 10px;
      width: 95%;
      margin: 10px auto;
      text-align: justify;
    }

    .none {
      text-justify: none;
    }

    .auto {
      text-justify: auto;
    }

    .dist {
      text-justify: distribute;
    }

    .word {
      text-justify: inter-word;
    }

    .char {
      text-justify: inter-character;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#text-justify-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'text-justify' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`text-justify`

32

`inter-word` and `distribute` (deprecated) values are supported, but `distribute` behavior is buggy.

12

Standard values `inter-character` and `none` are supported. The deprecated `distribute` value is also supported.

55

11

Standard values `inter-character` and `none` are supported. The deprecated `distribute` value is also supported.

19

`inter-word` and `distribute` (deprecated) values are supported, but `distribute` behavior is buggy.

No

See [bug 9945](https://webkit.org/b/99945).

No

32

`inter-word` and `distribute` (deprecated) values are supported, but `distribute` behavior is buggy.

55

19

`inter-word` and `distribute` (deprecated) values are supported, but `distribute` behavior is buggy.

No

See [bug 9945](https://webkit.org/b/99945).

No

## See also

- [`text-align`](text-align)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-justify" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-justify</a>
