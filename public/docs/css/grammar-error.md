# ::grammar-error

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `::grammar-error` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) represents a text segment which the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) has flagged as grammatically incorrect.

## Allowable properties

Only a small subset of CSS properties can be used in a rule with `::grammar-error` in its selector:

- [`color`](color)
- [`background-color`](background-color)
- [`cursor`](cursor)
- [`caret-color`](caret-color)
- [`outline`](outline) and its longhands
- [`text-decoration`](text-decoration) and its associated properties
- [`text-emphasis-color`](text-emphasis-color)
- [`text-shadow`](text-shadow)

## Syntax

    ::grammar-error

## Examples

### Simple document grammar check

In this example, eventual supporting browsers should highlight any flagged grammatical errors with the styles shown.

#### HTML

    <p>My friends is coming to the party tonight.</p>

#### CSS

    ::grammar-error  {
      text-decoration: underline red;
      color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#selectordef-grammar-error">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of '::grammar-error' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`::grammar-error`

No

No

No

No

No

No

See [bug 175784](https://webkit.org/b/175784).

No

No

No

No

No

No

## See also

- [`::spelling-error`](::spelling-error)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::grammar-error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::grammar-error</a>
