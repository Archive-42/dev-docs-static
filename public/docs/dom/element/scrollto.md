Element.scrollTo()
==================

The `scrollTo()` method of the [`Element`](../element) interface scrolls to a particular set of coordinates inside a given element.

Syntax
------

    element.scrollTo(x-coord, y-coord)
    element.scrollTo(options)

### Parameters

-   `x-coord` is the pixel along the horizontal axis of the element that you want displayed in the upper left.
-   `y-coord` is the pixel along the vertical axis of the element that you want displayed in the upper left.

\- or -

-   `options` is a [`ScrollToOptions`](../scrolltooptions) dictionary.

Examples
--------

    element.scrollTo(0, 1000);

Using `options`:

    element.scrollTo({
      top: 100,
      left: 100,
      behavior: 'smooth'
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scrollto-options-options">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'element.scrollTo()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scrollTo`

61

79

36

No

48

10.1

61

61

36

45

10.3

8.0

`ScrollToOptions`

61

79

Yes

No

48

No

61

61

Yes

45

No

8.0

See also
--------

-   [`Element.scrollTop`](scrolltop), [`Element.scrollLeft`](scrollleft)
-   [`Window.scrollTo()`](../window/scrollto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo</a>
