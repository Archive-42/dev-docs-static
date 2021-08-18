HTMLContentElement
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLContentElement` interface represents a [`<content>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content) HTML Element, which is used in [Shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM).

Properties
----------

*This interface inherits the properties of [`HTMLElement`](htmlelement).*

[`HTMLContentElement.select`](htmlcontentelement/select)  
Is a [`DOMString`](domstring) that reflects the [`select`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content#attr-select) HTML attribute. The value is a comma-separated list of CSS selectors that select the content to insert in place of the `<content>` element.

Methods
-------

*This interface inherits the methods of [`HTMLElement`](htmlelement).*

[`HTMLContentElement.getDistributedNodes()`](htmlcontentelement/getdistributednodes)  
Returns a static [`NodeList`](nodelist) of the <span class="page-not-created">distributed nodes</span> associated with this `<content>` element.

Specifications
--------------

This feature is no longer defined by any standards.

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

`HTMLContentElement`

35-89

79-89

28-52

No

26-75

No

37-89

37-89

28-52

26

No

3.0

`getDistributedNodes`

35-89

79-89

28-52

No

26-75

No

37-89

37-89

28-52

26

No

3.0

`select`

35-89

79-89

28-52

No

26-75

No

37-89

37-89

28-52

26

No

3.0

See also
--------

-   The [`<content>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content) HTML element, implementing this interface.
-   [Shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLContentElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLContentElement</a>
