# :host

The `:host` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) selects the shadow host of the [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) containing the CSS it is used inside — in other words, this allows you to select a custom element from inside its shadow DOM.

**Note**: This has no effect when used outside a shadow DOM.

    /* Selects a shadow root host */
    :host {
      font-weight: bold;
    }

## Syntax

    :host

## Examples

### Styling the shadow host

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

The `:host { background: rgba(0,0,0,0.1); padding: 2px 5px; }` rule styles all instances of the `<context-span>` element (the shadow host in this instance) in the document.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scoping/#host-selector">CSS Scoping Module Level 1<br />
<span class="small">The definition of ':host' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:host`

54

79

63

61-63

No

41

10

54

54

63

61-63

41

10

6.0

## See also

- [Web components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
- [`:host()`](<:host()>)
- [`:host-context()`](<:host-context()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:host" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:host</a>
