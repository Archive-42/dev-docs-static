# @charset

The `@charset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) specifies the character encoding used in the style sheet. It must be the first element in the style sheet and not be preceded by any character; as it is not a [nested statement](syntax#nested_statements), it cannot be used inside [conditional group at-rules](at-rule#conditional_group_rules). If several `@charset` at-rules are defined, only the first one is used, and it cannot be used inside a `style` attribute on an HTML element or inside the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element where the character set of the HTML page is relevant.

    @charset "utf-8";

This at-rule is useful when using non-ASCII characters in some CSS properties, like [`content`](content).

As there are several ways to define the character encoding of a style sheet, the browser will try the following methods in the following order (and stop as soon as one yields a result) :

1.  The value of the [Unicode byte-order](https://en.wikipedia.org/wiki/Byte_order_mark) character placed at the beginning of the file.
2.  The value given by the `charset` attribute of the `Content-Type:` HTTP header or the equivalent in the protocol used to serve the style sheet.
3.  The `@charset` CSS at-rule.
4.  Use the character encoding defined by the referring document: the `charset` attribute of the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element. This method is obsoleted in HTML5 and must not be used.
5.  Assume that the document is UTF-8

## Syntax

    @charset "UTF-8";
    @charset "iso-8859-15";

where:

_charset_  
Is a [`<string>`](string) denoting the character encoding to be used. It must be the name of a web-safe character encoding defined in the [IANA-registry](https://www.iana.org/assignments/character-sets), and must be double-quoted, following exactly one space character (U+0020), and immediately terminated with a semicolon. If several names are associated with an encoding, only the one marked with _preferred_ must be used.

## Formal syntax

    @charset "<charset>";

## Examples

### Valid and invalid charset declarations

    @charset "UTF-8";       /* Set the encoding of the style sheet to Unicode UTF-8 */
    @charset 'iso-8859-15'; /* Invalid, wrong quoting style used */
    @charset  "UTF-8";      /* Invalid, more than one space */
     @charset "UTF-8";      /* Invalid, there is a character (a space) before the at-rule */
    @charset UTF-8;         /* Invalid, without ' or ", the charset is not a CSS <string> */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#x57">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '@charset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`@charset`

2

12

1.5

Firefox 1 supported an invalid syntax where the character encoding is not between single or double quotes.

5.5

From Internet Explorer 5.5 to IE 7 (inclusive), Internet Explorer supported an invalid syntax where the character encoding is not between single or double quotes.

9

4

2

18

4

10.1

4

1.0

## See also

- [Character set](https://developer.mozilla.org/en-US/docs/Glossary/character_set) glossary entry
- [Unicode](https://developer.mozilla.org/en-US/docs/Glossary/Unicode) glossary entry

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@charset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@charset</a>
