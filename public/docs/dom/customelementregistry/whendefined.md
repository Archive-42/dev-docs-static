# CustomElementRegistry.whenDefined()

The `whenDefined()` method of the [`CustomElementRegistry`](../customelementregistry) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the named element is defined.

## Syntax

    customElements.whenDefined(name): Promise<CustomElementConstructor>;

### Parameters

name  
Custom element name.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will be fulfilled with the <a href="../window/customelements" id="custom-elements-api:custom-element-4">custom element</a>'s constructor when a <a href="../window/customelements" id="custom-elements-api:custom-element-5">custom element</a> becomes defined with the given name. (If such a <a href="../window/customelements" id="custom-elements-api:custom-element-6">custom element</a> is already defined, the returned promise will be immediately fulfilled.)

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SyntaxError</code></td><td>If the provided name is not a <a href="https://html.spec.whatwg.org/multipage/custom-elements.html#valid-custom-element-name">valid custom element name</a>, the promise rejects with a <code>SyntaxError</code>.</td></tr></tbody></table>

## Examples

This example uses `whenDefined()` to detect when the custom elements that make up a menu are defined. The menu displays placeholder content until the actual menu content is ready to display.

    <nav id="menu-container">
      <div class="menu-placeholder">Loading...</div>
      <nav-menu>
        <menu-item>Item 1</menu-item>
        <menu-item>Item 2</menu-item>
         ...
        <menu-item>Item N</menu-item>
      </nav-menu>
    </nav>

    const container = document.getElementById('menu-container');
    const placeholder = container.querySelector('.menu-placeholder');
    // Fetch all the children of menu that are not yet defined.
    const undefinedElements = container.querySelectorAll(':not(:defined)');

    const promises = [...undefinedElements].map(
      button => customElements.whenDefined(button.localName)
    );

    // Wait for all the children to be upgraded,
    // then remove the placeholder.
    await Promise.all(promises);
    container.removeChild(placeholder);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-customelementregistry-whendefined">HTML Living Standard<br />
<span class="small">The definition of 'customElements.whenDefined()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`whenDefined`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/whenDefined" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/whenDefined</a>
