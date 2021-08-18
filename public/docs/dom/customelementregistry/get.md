# CustomElementRegistry.get()

The `get()` method of the [`CustomElementRegistry`](../customelementregistry) interface returns the constructor for a previously-defined custom element.

## Syntax

    constructor = customElements.get(name);

### Parameters

name  
The name of the custom element whose constructor you want to return a reference to.

### Return value

The constructor for the named custom element, or `undefined` if there is no custom element definition with that name.

## Examples

    customElements.define('my-paragraph',
      class extends HTMLElement {
        constructor() {
          let templateContent = document.getElementById('my-paragraph').content;
          super() // returns element this scope
            .attachShadow({mode: 'open'}) // sets AND returns this.shadowRoot
            .append(templateContent.cloneNode(true));
      }
    })

    // Return a reference to the my-paragraph constructor
    let ctor = customElements.get('my-paragraph');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/custom-elements.html#dom-customelementregistry-get">HTML Living Standard<br />
<span class="small">The definition of 'customElements.get()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`get`

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

79

Support for 'Customized built-in elements' as well.

79

Support for 'Autonomous custom elements' only.

63

No

54

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.1

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

67

Support for 'Customized built-in elements' as well.

54

Support for 'Autonomous custom elements' only.

63

48

Support for 'Customized built-in elements' as well.

41

Support for 'Autonomous custom elements' only.

10.3

Supports 'Autonomous custom elements' but not 'Customized built-in elements'

9.0

Support for 'Customized built-in elements' as well.

6.0

Support for 'Autonomous custom elements' only.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/get</a>
