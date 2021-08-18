# :where()

The `:where()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) function takes a selector list as its argument, and selects any element that can be selected by one of the selectors in that list.

    /* Selects any paragraph inside a header, main
       or footer element that is being hovered */
    :where(header, main, footer) p:hover {
      color: red;
      cursor: pointer;
    }

    /* The above is equivalent to the following */
    header p:hover,
    main p:hover,
    footer p:hover {
      color: red;
      cursor: pointer;
    }

The difference between `:where()` and [`:is()`](:is) is that `:where()` always has 0 [specificity](specificity), whereas `:is()` takes on the specificity of the most specific selector in its arguments.

### Forgiving Selector Parsing

The specification defines `:is()` and `:where()` as accepting a [forgiving selector list](https://drafts.csswg.org/selectors-4/#typedef-forgiving-selector-list).

In CSS when using a selector list, if any of the selectors are invalid then the whole list is deemed invalid. When using `:is()` or `:where() `instead of the whole list of selectors being deemed invalid if one fails to parse, the incorrect or unsupported selector will be ignored and the others used.

    :where(:valid, :unsupported) {
      ...
    }

Will still parse correctly and match `:valid` even in browsers which don't support `:unsupported`, whereas:

    :valid, :unsupported {
      ...
    }

Will be ignored in browsers which don't support `:unsupported` even if they support `:valid`.

## Examples

### Comparing :where() and :is()

This example shows how `:where()` works, and also illustrates the difference between `:where()` and `:is()`.

Take the following HTML:

    <article>
      <h2>:is()-styled links</h2>
      <section class="is-styling">
        <p>Here is my main content. This <a href="https://mozilla.org">contains a link</a>.
      </section>

      <aside class="is-styling">
        <p>Here is my aside content. This <a href="https://developer.mozilla.org">also contains a link</a>.
      </aside>

      <footer class="is-styling">
        <p>This is my footer, also containing <a href="https://github.com/mdn">a link</a>.
      </footer>
    </article>

    <article>
      <h2>:where()-styled links</h2>
      <section class="where-styling">
        <p>Here is my main content. This <a href="https://mozilla.org">contains a link</a>.
      </section>

      <aside class="where-styling">
        <p>Here is my aside content. This <a href="https://developer.mozilla.org">also contains a link</a>.
      </aside>

      <footer class="where-styling">
        <p>This is my footer, also containing <a href="https://github.com/mdn">a link</a>.
      </footer>
    </article>

In this somewhat-contrived example, we have two articles that each contain a section, an aside, and a footer. They differ by the classes used to mark the child elements.

To make selecting the links inside them simpler, but still distinct, we _could_ use `:is()` or `:where()`, in the following manner:

    html {
      font-family: sans-serif;
      font-size: 150%;
    }

    :is(section.is-styling, aside.is-styling, footer.is-styling) a {
      color: red;
    }

    :where(section.where-styling, aside.where-styling, footer.where-styling) a {
      color: orange;
    }

However, what if we later want to override the color of links in the footers using a simple selector?

    footer a {
      color: blue;
    }

This won't work for the red links, because the selectors inside `:is()` count towards the specificity of the overall selector, and class selectors have a higher specificity than element selectors.

However, selectors inside `:where()` have specificity 0, so the orange footer link will be overridden by our simple selector.

**Note**: You can also find this example on GitHub; see [is-where](https://mdn.github.io/css-examples/is-where/).

## Syntax

    :where( <complex-selector-list> )where
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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#zero-matches">Selectors Level 4<br />
<span class="small">The definition of ':where()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:where`

88

72-88

88

78

77

Enabled by default in Firefox Nightly.

No

74

14

88

88

72-88

79

No

14

No

`forgiving_selector_list`

88

88

82

No

No

No

88

88

82

No

No

No

## See also

- [`:is()`](:is)
- [Selector list](selector_list)
- [Web components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:where" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:where</a>
