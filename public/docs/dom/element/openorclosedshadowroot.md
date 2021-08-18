# Element.openOrClosedShadowRoot

**Draft**

This page is not complete.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Note:** This API is available only to [WebExtensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions).

The `Element.openOrCloseShadowRoot` read-only property represents the shadow root hosted by the element, regardless if its [`mode`](../shadowroot/mode) is `open` or `closed`. Use [`Element.attachShadow()`](attachshadow) to add a shadow root to an existing element.

## Syntax

    var shadowroot = element.openOrCloseShadowRoot;

### Value

A [`ShadowRoot`](../shadowroot) object instance, regardless if its [`mode`](../shadowroot/mode) is set to `open` or `closed`, or `null` if no shadow root is present. (See [`Element.attachShadow()`](attachshadow) for further details).

## Specifications

_This property is not part of any specification._

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

`openOrClosedShadowRoot`

No

No

63

Available only to [WebExtensions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions).

No

No

No

No

No

63

Available only to [WebExtensions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions).

No

No

No

## See also

- [`Element.shadowRoot`](shadowroot)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/openOrClosedShadowRoot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/openOrClosedShadowRoot</a>
