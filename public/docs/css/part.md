# ::part()

The `::part` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) represents any element within a [shadow tree](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) that has a matching [`part`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-part) attribute.

    custom-element::part(foo) {
      /* Styles to apply to the `foo` part */
    }

## Syntax

    ::part( <ident>+ )

## Examples

### HTML

    <template id="tabbed-custom-element">
    <style type="text/css">
    *, ::before, ::after {
      box-sizing: border-box;
      padding: 1rem;
    }
    :host {
      display: flex;
    }
    </style>
    <div part="tab active">Tab 1</div>
    <div part="tab">Tab 2</div>
    <div part="tab">Tab 3</div>
    </template>

    <tabbed-custom-element></tabbed-custom-element>

### CSS

    tabbed-custom-element::part(tab) {
      color: #0c0dcc;
      border-bottom: transparent solid 2px;
    }

    tabbed-custom-element::part(tab):hover {
      background-color: #0c0d19;
      border-color: #0c0d33;
    }

    tabbed-custom-element::part(tab):hover:active {
      background-color: #0c0d33;
    }

    tabbed-custom-element::part(tab):focus {
      box-shadow:
        0 0 0 1px #0a84ff inset,
        0 0 0 1px #0a84ff,
        0 0 0 4px rgba(10, 132, 255, 0.3);
    }

    tabbed-custom-element::part(active) {
      color: #0060df;
      border-color: #0a84ff !important;
    }

### JavaScript

    let template = document.querySelector("#tabbed-custom-element");
    globalThis.customElements.define(template.id, class extends HTMLElement {
      constructor() {
        super();
        this.attachShadow({ mode: "open" });
        this.shadowRoot.appendChild(template.content);
      }
    });

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shadow-parts-1/#part">Shadow Parts<br />
<span class="small">The definition of '::part' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`::part`

73

79

72

69-72

No

60

13.1

73

73

No

52

13.4

11.0

## See also

- The [`part`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-part) attribute - Used to define parts which can be selected by the `::part()` selector
- The [`exportparts`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-exportparts) attribute - Used to transitively export shadow parts from a nested shadow tree into a containing light tree.
- [Explainer: CSS Shadow ::part and ::theme](https://github.com/fergald/docs/blob/master/explainers/css-shadow-parts-1.md)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::part" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::part</a>
