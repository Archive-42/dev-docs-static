# :not()

The `:not()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents elements that do not match a list of selectors. Since it prevents specific items from being selected, it is known as the _negation pseudo-class_.

    /* Selects any element that is NOT a paragraph */
    :not(p) {
      color: blue;
    }

The `:not()` pseudo-class has a number of [quirks, tricks, and unexpected results](#description) that you should be aware of before using it.

## Syntax

The `:not()` pseudo-class requires a comma-separated list of one or more selectors as its argument. The list must not contain another negation selector or a [pseudo-element](pseudo-elements).

The ability to list more than one selector is experimental and not yet widely supported.

    :not( <complex-selector-list> )where
    <complex-selector-list> = <complex-selector>#where
    <complex-selector> = <compound-selector> [ <combinator>? <compound-selector> ]*where
    <compound-selector> = [ <type-selector>? <subclass-selector>* [ <pseudo-element-selector> <pseudo-class-selector>* ]* ]!
    <combinator> = '>' | '+' | '~' | [ '||' ]where
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

There are several unusual effects and outcomes when using `:not()` that you should keep in mind when using it:

- The `:not` pseudo-class may not be nested, which means that `:not(:not(...))` is invalid.
- Useless selectors can be written using this pseudo-class. For example, `:not(*)` matches any element which is not an element, which is obviously nonsense, so the accompanying rule will never be applied.
- This pseudo-class can increase the [specificity](specificity) of a rule. For example, `#foo:not(#bar)` will match the same element as the simpler `#foo`, but has a higher specificity.
- `:not(.foo)` will match anything that isn't `.foo`, _including [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) and [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)._
- This selector only applies to one element; you cannot use it to exclude all ancestors. For instance, `body :not(table) a` will still apply to links inside of a table, since [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) will match with the `:not()` part of the selector.
- Using two selectors at the same time is not yet supported in all browsers. Example: `:not(.foo, .bar)`. For wider support you could use, `:not(.foo):not(.bar)`

## Examples

### Basic set of :not() examples

#### HTML

    <p>I am a paragraph.</p>
    <p class="fancy">I am so very fancy!</p>
    <div>I am NOT a paragraph.</div>
    <h2>
      <span class="foo">foo inside h2</span>
      <span class="bar">bar inside h2</span>
    </h2>

#### CSS

    .fancy {
      text-shadow: 2px 2px 3px gold;
    }

    /* <p> elements that are not in the class `.fancy` */
    p:not(.fancy) {
      color: green;
    }

    /* Elements that are not <p> elements */
    body :not(p) {
      text-decoration: underline;
    }

    /* Elements that are not <div> and not <span> elements */
    body :not(div):not(span) {
      font-weight: bold;
    }

    /* Elements that are not <div>s or `.fancy` */
    /* Note that this syntax is not well supported yet. */
    body :not(div, .fancy) {
      text-decoration: overline underline;
    }

    /* Elements inside an <h2> that aren't a <span> with a class of foo. */
    /* Complex selectors such as an element with a class are not well supported yet. */
    h2 :not(span.foo) {
      color: red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#negation">Selectors Level 4<br />
<span class="small">The definition of ':not()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Extends its argument to allow some non-simple selectors.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#negation">Selectors Level 3<br />
<span class="small">The definition of ':not()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

- [Pseudo-classes](pseudo-classes)
- [Pseudo-classes and pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)
- Related CSS pseudo-classes:
  - [`:has()`](:has)
  - [`:is()`](:is)
  - [`:where()`](:where)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:not" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:not</a>
