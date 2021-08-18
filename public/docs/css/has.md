# :has()

The `:has()` CSS [pseudo-class](pseudo-classes) represents an element if any of the selectors passed as parameters (relative to the [`:scope`](:scope) of the given element) match at least one element.

    /* Selects any <a>, as long as it has an <img> element directly inside it  */
    /* Note that this is not supported in any browser yet */
    let test = document.querySelector('a:has(> img)');

## Syntax

    :has( <relative-selector-list> )where
    <relative-selector-list> = <relative-selector>#where
    <relative-selector> = <combinator>? <complex-selector>where
    <combinator> = '>' | '+' | '~' | [ '||' ]
    <complex-selector> = <compound-selector> [ <combinator>? <compound-selector> ]*where
    <compound-selector> = [ <type-selector>? <subclass-selector>* [ <pseudo-element-selector> <pseudo-class-selector>* ]* ]!
    where
    <type-selector> = <wq-name> | <ns-prefix>? '*'
    <subclass-selector> = <id-selector> | <class-selector> | <attribute-selector> | <pseudo-class-selector>
    <pseudo-element-selector> = ':' <pseudo-class-selector>
    <pseudo-class-selector> = ':' <ident-token> | ':' <function-token> <any-value> ')'where
    <wq-name> = <ns-prefix>? <ident-token>
    <ns-prefix> = [ <ident-token> | '*' ]?  |
    <id-selector> = <hash-token>
    <class-selector> = '.' <ident-token>
    <attribute-selector> = '[' <wq-name> ']' | '[' <wq-name> <attr-matcher> [ <string-token> | <ident-token> ] <attr-modifier>? ']'
    where
    <attr-matcher> = [ '~' |  |  | '^' | '$' | '*' ]? '='
    <attr-modifier> = i | s

## Description

The `:has()` pseudo-class takes a relative selector list as an argument. In earlier revisions of the CSS Selectors Level 4 specification, `:has` had a limitation that it couldn't be used within stylesheets. Instead, it could only be used with functions like [`document.querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector); this was due to performance concerns. _This limitation has been removed_ because no browser implemented it that way. Instead, browsers currently only support the use of `:has()` within stylesheets.

## Examples

### Matching &lt;a&gt; elements that directly contain an &lt;img&gt;

The following selector matches only [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) elements that directly contain an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) child:

    a:has(> img)

### Matching &lt;h1&gt; elements that are followed by a &lt;p&gt;

The following selector matches [`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) elements only if they have a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element directly following them:

    h1:has(+ p)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#relational">Selectors Level 4<br />
<span class="small">The definition of ':has()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`:has`

No

See [bug 669058](https://crbug.com/669058)

No

See [bug 669058](https://crbug.com/669058)

No

See [bug 418039](https://bugzil.la/418039)

No

No

No

No

No

No

See [bug 418039](https://bugzil.la/418039)

No

No

No

## See also

- [Locating DOM elements using selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)
- `:scope`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:has</a>
