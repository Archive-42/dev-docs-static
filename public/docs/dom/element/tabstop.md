Element.tabStop
===============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `tabStop` property of the [`Element`](../element) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element can receive input focus via the tab key. If the specified element is a shadow host tab navigation is delegated to its children.

This property was proposed to add tab functionality for Custom Elements. While with the existing [`tabIndex`](../htmlorforeignelement/tabindex) property, it is required to specify an order for the element to become tabbable. The `tabStop` property would decouple the tabbable property from the tab index. After feedback, this property was removed from the [design doc](https://docs.google.com/document/d/1k93Ez6yNSyWQDtGjdJJqTBPmljk9l2WS3JTe5OHHB50/edit) and replaced by [`ShadowRoot.delegatesFocus`](../shadowroot/delegatesfocus).

Syntax
------

    var isTabStop = element.tabStop;
    element.tabStop = (true|false);

Example
-------

    // TBD

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

`tabStop`

No

No

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/tabStop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/tabStop</a>
