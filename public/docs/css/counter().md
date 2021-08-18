# counter()

The `counter()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) returns a string representing the current value of the named counter, if there is one. It is generally used with [pseudo-elements](pseudo-elements), but can be used, theoretically, anywhere a `<string>` value is supported.

    /* Simple usage */
    counter(countername);

    /* changing the counter display */
    counter(countername, upper-roman)

A [counter](css_lists_and_counters/using_css_counters) has no visible effect by itself. The `counter()` function (and [`counters()`](<counters()>) function) is what makes it useful by returning developer defined strings (or images).

**Note:** The `counter()` function can be used with any CSS property, but support for properties other than [`content`](content) is experimental, and support for the type-or-unit parameter is sparse.

Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

## Syntax

### Values

[`<custom-ident>`](custom-ident)  
A name identifying the counter, which is the same case-sensitive name used for the [`counter-reset`](counter-reset) and [`counter-increment`](counter-increment). The name cannot start with two dashes and can't be `none`, `unset`, `initial`, or `inherit`.

`<counter-style>`  
A [`<list-style-type>`](list-style-type) name, [`<@counter-style>`](@counter-style) name or [`symbols()`](<symbols()>) function, where a counter style name is a `numeric`, `alphabetic`, or `symbolic` simple predefined counter style, a complex longhand east Asian or Ethiopic predefined counter style, or other [predefined counter style](css_counter_styles). If omitted, the counter-style defaults to `decimal`.

### Formal syntax

    counter( <custom-ident>, <counter-style>? )where
    <counter-style> = <counter-style-name> | symbols()where
    <counter-style-name> = <custom-ident>

## Examples

### default value compared to upper Roman

#### HTML

    <ol>
      <li></li>
      <li></li>
      <li></li>
    </ol>

#### CSS

    ol {
      counter-reset: listCounter;
    }
    li {
      counter-increment: listCounter;
    }
    li::after {
      content: "[" counter(listCounter) "] == ["
                   counter(listCounter, upper-roman) "]";
    }

#### Result

### decimal-leading-zero compared to lower-alpha

#### HTML

    <ol>
      <li></li>
      <li></li>
      <li></li>
    </ol>

#### CSS

    ol {
      counter-reset: count;
    }
    li {
      counter-increment: count;
    }
    li::after {
      content: "[" counter(count, decimal-leading-zero) "] == ["
                   counter(count, lower-alpha) "]";
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

`counter()`

1

12

1

8

9.2

3

≤37

18

4

10.1

1

1.0

## See also

- [Using CSS Counters](css_lists_and_counters/using_css_counters)
- [`counter-reset`](counter-reset)
- [`counter-set`](counter-set)
- [`counter-increment`](counter-increment)
- [`@counter-style`](@counter-style)
- CSS `counters()` function

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/counter()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/counter()</a>
