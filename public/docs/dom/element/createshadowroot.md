Element.createShadowRoot()
==========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Draft**

This page is not complete.

Use `Element.createShadowRoot` to create an instance of [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM). When shadow DOM is created, it is always attached to an existing element. After the shadow DOM is created, the element that it is attached to is called the <span class="page-not-created">shadow root</span>.

This method has been deprecated in favor of [`attachShadow()`](attachshadow).

Syntax
------

    var shadowroot = element.createShadowRoot();

### Parameters

No parameters.

### Result value

Returns a [`ShadowRoot`](../shadowroot).

Specifications
--------------

This feature is no longer defined by any specifications.

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

`createShadowRoot`

35

In Chrome 45, the ability to have multiple shadow roots was deprecated.

25-36

79

59-61

29-59

No

22

In Opera 32, the ability to have multiple shadow roots was deprecated.

15-23

No

37

In version 45, the ability to have multiple shadow roots was deprecated.

4.4-37

35

In Chrome 45, the ability to have multiple shadow roots was deprecated.

25-36

59-61

29-59

22

In Opera 32, the ability to have multiple shadow roots was deprecated.

14-24

No

3.0

In Samsung Internet 5.0, the ability to have multiple shadow roots was deprecated.

1.5-3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/createShadowRoot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/createShadowRoot</a>
