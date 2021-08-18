# Element.shadowRoot

The `Element.shadowRoot` read-only property represents the shadow root hosted by the element. Use [`Element.attachShadow()`](attachshadow) to add a shadow root to an existing element.

## Syntax

    var shadowroot = element.shadowRoot;

### Value

A [`ShadowRoot`](../shadowroot) object instance, or `null` if the associated shadow root was attached with its [`mode`](../shadowroot/mode) set to `closed`. (See [`Element.attachShadow()`](attachshadow) for further details).

## Examples

The following snippets are taken from our [life-cycle-callbacks](https://github.com/mdn/web-components-examples/tree/master/life-cycle-callbacks) example ([see it live also](https://mdn.github.io/web-components-examples/life-cycle-callbacks)), which creates an element that displays a square of a size and color specified in the element's attributes.

Inside the `<custom-square>` element's class definition we include some life cycle callbacks that make a call to an external function, `updateStyle()`, which actually applies the size and color to the element. You'll see that we are passing it `this` (the custom element itself) as a parameter.

    connectedCallback() {
      console.log('Custom square element added to page.');
      updateStyle(this);
    }

    attributeChangedCallback(name, oldValue, newValue) {
      console.log('Custom square element attributes changed.');
      updateStyle(this);
    }

In the `updateStyle()` function itself, we get a reference to the shadow DOM using [`Element.shadowRoot`](shadowroot). From here we use standard DOM traversal techniques to find the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element inside the shadow DOM and then update the CSS found inside it:

    function updateStyle(elem) {
      const shadow = elem.shadowRoot;
      const childNodes = Array.from(shadow.childNodes);

      childNodes.forEach(childNode => {
        if (childNode.nodeName === 'STYLE') {
          childNode.textContent = `
            div {
              width: ${elem.getAttribute('l')}px;
              height: ${elem.getAttribute('l')}px;
              background-color: ${elem.getAttribute('c')};
            }
          `;
        }
      });
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-shadowroot">DOM<br />
<span class="small">The definition of 'shadowRoot' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`shadowRoot`

35

79

63

No

22

10

37

35

63

22

10

3.0

## See also

- [`Element.openOrClosedShadowRoot`](openorclosedshadowroot) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/shadowRoot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/shadowRoot</a>
