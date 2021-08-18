# :host-context()

The `:host-context()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) function selects the shadow host of the [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) containing the CSS it is used inside (so you can select a custom element from inside its shadow DOM) — but only if the selector given as the function's parameter matches the shadow host's ancestor(s) in the place it sits inside the DOM hierarchy.

In other words, this allows a custom element, or anything within that custom element's shadow DOM, to apply different styles based on its position within the outer DOM or classes/attributes applied to ancestor elements.

One typical use of this is with a descendant selector expression — for example `h1` — to select only instances of the custom element that are inside an `<h1>`. Another typical use would be to allow inner elements to react to classes or attributes on any ancestor elements - for example, applying a different text color when a `.dark-theme` class is applied to `<body>`.

**Note**: This has no effect when used outside a shadow DOM.

    /* Selects a shadow root host, only if it is
       a descendant of the selector argument given */
    :host-context(h1) {
      font-weight: bold;
    }

    :host-context(main article) {
      font-weight: bold;
    }

    /* Changes paragraph text color from black to white when
       a .dark-theme class is applied to the document body */
    p {
      color: #000;
    }

    :host-context(body.dark-theme) p {
      color: #fff;
    }

## Syntax

    :host-context( <compound-selector-list> )where
    <compound-selector-list> = <compound-selector>#where
    <compound-selector> = [ <type-selector>? <subclass-selector>* [ <pseudo-element-selector> <pseudo-class-selector>* ]* ]!where
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

## Examples

### Selectively styling shadow hosts

The following snippets are taken from our [host-selectors example](https://github.com/mdn/web-components-examples/tree/master/host-selectors) ([see it live also](https://mdn.github.io/web-components-examples/host-selectors/)).

In this example we have a simple custom element — `<context-span>` — that you can wrap around text:

    <h1>Host selectors <a href="#"><context-span>example</context-span></a></h1>

Inside the element's constructor, we create `style` and `span` elements, fill the `span` with the content of the custom element, and fill the `style` element with some CSS rules:

    let style = document.createElement('style');
    let span = document.createElement('span');
    span.textContent = this.textContent;

    const shadowRoot = this.attachShadow({mode: 'open'});
    shadowRoot.appendChild(style);
    shadowRoot.appendChild(span);

    style.textContent = 'span:hover { text-decoration: underline; }' +
                        ':host-context(h1) { font-style: italic; }' +
                        ':host-context(h1):after { content: " - no links in headers!" }' +
                        ':host-context(article, aside) { color: gray; }' +
                        ':host(.footer) { color : red; }' +
                        ':host { background: rgba(0,0,0,0.1); padding: 2px 5px; }';

The `:host-context(h1) { font-style: italic; }` and `:host-context(h1):after { content: " - no links in headers!" }` rules style the instance of the `<context-span>` element (the shadow host in this instance) inside the `<h1>`. We've used it to make it clear that the custom element shouldn't appear inside the `<h1>` in our design.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scoping/#host-selector">CSS Scoping Module Level 1<br />
<span class="small">The definition of ':host-context()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:host-context()`

54

79

No

See [bug 1082060](https://bugzil.la/1082060).

No

41

No

54

54

No

See [bug 1082060](https://bugzil.la/1082060).

41

No

6.0

## See also

- [Web components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
- [`:host`](:host)
- [`:host()`](<:host()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context()</a>
