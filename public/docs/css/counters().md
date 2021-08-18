# counters()

The `counters()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) enables nested counters, returning a concatenated string representing the current values of the named counters, if there are any. The `counters()` function has two forms: `counters(name, string)` or `counters(name, string, style)`. It is generally used with [pseudo-elements](pseudo-elements), but can be used, theoretically, anywhere a `<string>` value is supported. The generated text is the value of all counters with the given name, from outermost to innermost, separated by the specified string. The counters are rendered in the style indicated, defaulting to `decimal` if no style is specified.

    /* Simple usage  - style defaults to decimal */
    counters(countername, '-');

    /* changing the counter display */
    counters(countername, '.', upper-roman)

A [counter](css_lists_and_counters/using_css_counters) has no visible effect by itself. The `counters()` function (and [`counter()`](<counter()>) function) is what makes it useful by returning developer defined content.

**Note:** The `counters()` function can be used with any CSS property, but support for properties other than [`content`](content) is experimental, and support for the type-or-unit parameter is sparse.

Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

## Syntax

### Values

[`<custom-ident>`](custom-ident)  
A name identifying the counters, which is the same case-sensitive name used for the [`counter-reset`](counter-reset) and [`counter-increment`](counter-increment). The name cannot start with two dashes and can't be `none`, `unset`, `initial`, or `inherit`.

`<counter-style>`  
A counter style name or `symbols()` function, where a counter style name is a numeric, alphabetic, or symbolic simple predefined counter style, a complex longhand east Asian or Ethiopic predefined counter style, or other [predefined counter style](css_counter_styles). If omitted, the counter-style defaults to decimal

[`<string>`](string)  
Any number of text characters. Non-Latin characters must be encoded using their Unicode escape sequences: for example, `\000A9` represents the copyright symbol.

### Formal syntax

    counters( <custom-ident>, <string>, <counter-style>? )where
    <counter-style> = <counter-style-name> | symbols()where
    <counter-style-name> = <custom-ident>

## Examples

### default value compared to upper Roman

#### HTML

    <ol>
      <li>
         <ol>
            <li></li>
            <li></li>
            <li></li>
          </ol>
      </li>
      <li></li>
      <li></li>
      <li>
         <ol>
            <li></li>
            <li>
               <ol>
                  <li></li>
                  <li></li>
                  <li></li>
               </ol>
            </li>
          </ol>
      </li>
    </ol>

#### CSS

    ol {
      counter-reset: listCounter;
    }
    li {
      counter-increment: listCounter;
    }
    li::marker {
       content:  counters(listCounter, '.', upper-roman) ') ';
    }
    li::before {
      content:  counters(listCounter, ".") " == " counters(listCounter, ".", lower-roman) ;
    }

#### Result

### decimal-leading-zero compared to lower-alpha

#### HTML

    <ol>
      <li>
         <ol>
            <li></li>
            <li></li>
            <li></li>
          </ol>
      </li>
      <li></li>
      <li></li>
      <li>
         <ol>
            <li></li>
            <li>
               <ol>
                  <li></li>
                  <li></li>
                  <li></li>
               </ol>
            </li>
          </ol>
      </li>
    </ol>

#### CSS

    ol {
      counter-reset: count;
    }
    li {
      counter-increment: count;
    }
    li::marker {
       content: counters(count, '.', upper-alpha) ') ';
    }
    li::before {
      content: counters(count, ".", decimal-leading-zero) " == " counters(count, ".", lower-alpha);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#counter-functions">CSS Lists Module Level 3<br />
<span class="small">The definition of 'CSS Counters' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#counter-styles">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'CSS Counters' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`counters()`

1

12

1.5

8

10

3

1

18

4

10.1

1

1.0

## See also

- [Using CSS Counters](css_lists_and_counters/using_css_counters)
- [`counter-set`](counter-set)
- [`counter-reset`](counter-reset)
- [`counter-increment`](counter-increment)
- [`@counter-style`](@counter-style)
- CSS `counter()` function
- [`::marker`](::marker)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/counters()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/counters()</a>
