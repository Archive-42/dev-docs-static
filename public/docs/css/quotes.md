# quotes

The `quotes` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how the browser should render quotation marks that are added using the `open-quotes` or `close-quotes` values of the CSS `content` property.

## Syntax

    /* Keyword value */
    quotes: none;
    quotes: auto;

    /* <string> values */
    quotes: "«" "»";           /* Set open-quote and close-quote to the French quotation marks */
    quotes: "«" "»" "‹" "›";   /* Set two levels of quotation marks */

    /* Global values */
    quotes: inherit;
    quotes: initial;
    quotes: unset;

### Values

`none`  
The `open-quote` and `close-quote` values of the [`content`](content) property produce no quotation marks.

`auto`  
Appropriate quote marks will be used for whatever language value is set on the selected elements (i.e. via the [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-lang) attribute).

`[<string> <string>]+`  
One or more pairs of [`<string>`](string) values for `open-quote` and `close-quote`. The first pair represents the outer level of quotation, the second pair is for the first nested level, next pair for third level and so on.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>depends on user agent</td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | auto | [ <string> <string> ]+

## Examples

### Basic quote marks

#### HTML

    <q>To be or not to be. That's the question!</q>

#### CSS

    q {
      quotes: '"' '"' "'" "'";
    }
    q::before {
      content: open-quote;
    }
    q::after {
      content: close-quote;
    }

#### Result

### Auto quotes

For most browsers, the default value of `quotes` is `auto` (Firefox 70+), or the browser otherwise had this default behavior (Chromiums, Safari, Edge), so this example works without it being explicitly being set.

#### HTML

    <div lang="fr">
      <q>Ceci est une citation française.</q>
    <div>
    <hr>
    <div lang="ru">
      <q>Это русская цитата</q>
    <div>
    <hr>
    <div lang="de">
      <q>Dies ist ein deutsches Zitat</q>
    <div>
    <hr>
    <div lang="en">
      <q>This is an English quote.</q>
    <div>

#### CSS

    /*q {
      quotes: auto;
    }*/

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-content-3/#quotes">CSS Generated Content Module Level 3<br />
<span class="small">The definition of 'quotes' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#quotes">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'quotes' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`quotes`

11

12

1.5

8

4

9

37

18

4

14

9

1.0

`quotes_auto`

87

87

70

No

This value is not supported, but the default browser behavior is to choose appropriate quotes for the user's language setting

73

No

This value is not supported, but the default browser behavior is to choose appropriate quotes for the user's language setting

87

87

No

No

This value is not supported, but the default browser behavior is to choose appropriate quotes for the user's language setting

No

This value is not supported, but the default browser behavior is to choose appropriate quotes for the user's language setting

No

This value is not supported, but the default browser behavior is to choose appropriate quotes for the user's language setting

## See also

- [`content`](content)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/quotes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/quotes</a>
