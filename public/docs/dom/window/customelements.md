Window.customElements
=====================

The `customElements` read-only property of the [`Window`](../window) interface returns a reference to the [`CustomElementRegistry`](../customelementregistry) object, which can be used to register new [custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) and get information about previously registered custom elements.

Examples
--------

The most common example you'll see of this property being used is to get access to the [`CustomElementRegistry.define()`](../customelementregistry/define) method to define and register a new custom element, e.g.:

    let customElementRegistry = window.customElements;
    customElementRegistry.define('my-custom-element', MyCustomElement);

However, it is usually shortened to something like the following:

    customElements.define('element-details',
      class extends HTMLElement {
        constructor() {
          super();
          const template = document
            .getElementById('element-details-template')
            .content;
          const shadowRoot = this.attachShadow({mode: 'open'})
            .appendChild(template.cloneNode(true));
        }
      }
    );

See our [web-components-examples](https://github.com/mdn/web-components-examples/) repo for more usage examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/custom-elements.html#dom-window-customelements">HTML Living Standard<br />
<span class="small">The definition of 'window.customElements' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`customElements`

54

79

63

No

41

10.1

54

54

63

41

10.3

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/customElements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/customElements</a>
