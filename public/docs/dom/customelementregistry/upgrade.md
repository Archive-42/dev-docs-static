# CustomElementRegistry.upgrade()

The `upgrade()` method of the [`CustomElementRegistry`](../customelementregistry) interface upgrades all shadow-containing custom elements in a [`Node`](../node) subtree, even before they are connected to the main document.

## Syntax

    customElements.upgrade(root);

### Parameters

`root`  
A [`Node`](../node) instance with shadow-containing descendant elements that are to be upgraded. If there are no descendant elements that can be upgraded, no error is thrown.

### Return value

Void.

## Examples

Taken from the [HTML spec](https://html.spec.whatwg.org/multipage/custom-elements.html#dom-customelementregistry-upgrade):

    const el = document.createElement("spider-man");

    class SpiderMan extends HTMLElement {}
    customElements.define("spider-man", SpiderMan);

    console.assert(!(el instanceof SpiderMan)); // not yet upgraded

    customElements.upgrade(el);
    console.assert(el instanceof SpiderMan);    // upgraded!

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/custom-elements.html#dom-customelementregistry-upgrade">HTML Living Standard<br />
<span class="small">The definition of 'customElements.upgrade()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`upgrade`

68

79

63

No

55

12.1

68

68

63

48

12.2

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/upgrade" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry/upgrade</a>
