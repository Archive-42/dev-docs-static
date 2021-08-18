# unicode-bidi

The `unicode-bidi` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property, together with the [`direction`](direction) property, determines how bidirectional text in a document is handled. For example, if a block of content contains both left-to-right and right-to-left text, the user-agent uses a complex Unicode algorithm to decide how to display the text. The `unicode-bidi` property overrides this algorithm and allows the developer to control the text embedding.

The `unicode-bidi` and [`direction`](direction) properties are the only properties that are not affected by the [`all`](all) shorthand.

**Note:** This property is intended for Document Type Definition (DTD) designers. Web designers and similar authors **should not** override it.

    /* Keyword values */
    unicode-bidi: normal;
    unicode-bidi: embed;
    unicode-bidi: isolate;
    unicode-bidi: bidi-override;
    unicode-bidi: isolate-override;
    unicode-bidi: plaintext;
    /* Global values */
    unicode-bidi: inherit;
    unicode-bidi: initial;
    unicode-bidi: unset;

## Syntax

### Values

`normal`  
The element does not offer an additional level of embedding with respect to the bidirectional algorithm. For inline elements, implicit reordering works across element boundaries.

`embed`  
If the element is inline, this value opens an additional level of embedding with respect to the bidirectional algorithm. The direction of this embedding level is given by the [`direction`](direction) property.

`bidi-override`  
For inline elements this creates an override. For block container elements this creates an override for inline-level descendants not within another block container element. This means that inside the element, reordering is strictly in sequence according to the [`direction`](direction) property; the implicit part of the bidirectional algorithm is ignored.

`isolate`  
This keyword indicates that the element's container directionality should be calculated without considering the content of this element. The element is therefore _isolated_ from its siblings. When applying its bidirectional-resolution algorithm, its container element treats it as one or several `U+FFFC Object Replacement Character`, i.e. like an image.

`isolate-override`  
This keyword applies the isolation behavior of the `isolate` keyword to the surrounding content and the override behavior of the `bidi-override` keyword to the inner content.

`plaintext`  
This keyword makes the elements directionality calculated without considering its parent bidirectional state or the value of the [`direction`](direction) property. The directionality is calculated using the P2 and P3 rules of the Unicode Bidirectional Algorithm.  
This value allows the display of data that is already formatted using a tool following the Unicode Bidirectional Algorithm.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, though some values have no effect on non-inline elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | embed | isolate | bidi-override | isolate-override | plaintext

## Examples

### CSS

    .bible-quote {
      direction: rtl;
      unicode-bidi: embed;
    }

### HTML

    <div class="bible-quote">
      A line of text
    </div>
    <div>
      Another line of text
    </div>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-writing-modes-3/#unicode-bidi">CSS Writing Modes Module Level 3<br />
<span class="small">The definition of 'unicode-bidi' in that specification.</span></a></td><td><span class="spec-pr">Proposed Recommendation</span></td><td>Added <code>plaintext</code>, <code>isolate</code>, and <code>isolate-override</code> keywords.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#propdef-unicode-bidi">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'unicode-bidi' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`unicode-bidi`

2

12

1

5.5

9.2

1.3

1

18

4

10.1

3.1

1.0

`isolate`

48

16

\["Avoiding using `-webkit-isolate`. It can lock up older versions of Safari (up to version 9) and Chrome (up to version 47).", "Since Chrome 19, the syntax from a previous version of the specification, where the `isolate` keyword could be used together with `bidi-override`, is allowed."\]

79

79

50

10-54

From Firefox 10 to Firefox 16 (inclusive), the `isolate` keyword could be used together with `bidi-override`, which was the syntax from a previous version of the specification. From Firefox 17, only one value is allowed. Use `isolate-override` instead the previous `isolate bidi-override`.

No

35

15

\["Avoiding using `-webkit-isolate`. It can lock up older versions of Opera (up to version 34).", "The syntax from a previous version of the specification, where the `isolate` keyword could be used together with `bidi-override`, is allowed."\]

11

6

Avoiding using `-webkit-isolate`. It can lock up older versions of Safari (up to version 9) and Chrome (up to version 47).

48

48

50

10-54

From Firefox 10 to Firefox 16 (inclusive), the `isolate` keyword could be used together with `bidi-override`, which was the syntax from a previous version of the specification. From Firefox 17, only one value is allowed. Use `isolate-override` instead the previous `isolate bidi-override`.

35

11

6

Avoiding using `-webkit-isolate`. It can lock up older versions of Safari (up to version 9) and Chrome (up to version 47).

5.0

`isolate-override`

48

79

50

17-54

No

35

11

6.1

48

48

50

17-54

35

11

7

5.0

`plaintext`

48

79

50

10-54

\["Before Firefox 50, the `plaintext` value was ignored for vertical writing modes ([bug 1302734](https://bugzil.la/1302734)).", "Before Firefox 15, `plaintext` didn't do anything to an inline element. The specification changed and the implementation was changed in Firefox 15."\]

No

35

11

6

48

48

50

10-54

\["Before Firefox 50, the `plaintext` value was ignored for vertical writing modes ([bug 1302734](https://bugzil.la/1302734)).", "Before Firefox 15, `plaintext` didn't do anything to an inline element. The specification changed and the implementation was changed in Firefox 15."\]

35

11

6

5.0

## See also

- [`direction`](direction)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/unicode-bidi</a>
