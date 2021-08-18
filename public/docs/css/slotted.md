# ::slotted()

The `::slotted()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) represents any element that has been placed into a slot inside an HTML template (see [Using templates and slots](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots) for more information).

This only works when used inside CSS placed within a [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM). Note also that this selector won't select a text node placed into a slot; it only targets actual elements.

    /* Selects any element placed inside a slot */
    ::slotted(*) {
      font-weight: bold;
    }

    /* Selects any <span> placed inside a slot */
    ::slotted(span) {
      font-weight: bold;
    }

## Syntax

    ::slotted( <compound-selector-list> )where
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

### Highlighting slotted elements

The following snippets are taken from our [slotted-pseudo-element](https://github.com/mdn/web-components-examples/tree/master/slotted-pseudo-element) demo ([see it live also](https://mdn.github.io/web-components-examples/slotted-pseudo-element/)).

In this demo we use a simple template with three slots:

    <template id="person-template">
      <div>
        <h2>Personal ID Card</h2>
        <slot name="person-name">NAME MISSING</slot>
        <ul>
          <li><slot name="person-age">AGE MISSING</slot></li>
          <li><slot name="person-occupation">OCCUPATION MISSING</slot></li>
        </ul>
      </div>
    </template>

A custom element — `<person-details>` — is defined like so:

    customElements.define('person-details',
      class extends HTMLElement {
        constructor() {
          super();
          let template = document.getElementById('person-template');
          let templateContent = template.content;

          const shadowRoot = this.attachShadow({mode: 'open'});

          let style = document.createElement('style');
          style.textContent = 'div { padding: 10px; border: 1px solid gray; width: 200px; margin: 10px; }' +
                               'h2 { margin: 0 0 10px; }' +
                               'ul { margin: 0; }' +
                               'p { margin: 10px 0; }' +
                               '::slotted(*) { color: gray; font-family: sans-serif; } ';

          shadowRoot.appendChild(style);
          shadowRoot.appendChild(templateContent.cloneNode(true));
      }
    })

You'll see that when filling the `style` element with content, we select all slotted elements (`::slotted(*)`) and give them a different font and color. This allows them to stand out better next to the slots that haven't been successfully filled.

The element looks like this when inserted into the page:

    <person-details>
      <p slot="person-name">Dr. Shazaam</p>
      <span slot="person-age">Immortal</span>
      <span slot="person-occupation">Superhero</span>
    </person-details>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scoping/#slotted-pseudo">CSS Scoping Module Level 1<br />
<span class="small">The definition of '::slotted' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`::slotted`

50

79

63

59-63

No

37

10

50

50

63

59-63

37

10

5.0

## See also

- [Web components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted</a>
