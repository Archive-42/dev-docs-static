HTMLTableElement.bgColor
========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLTableElement.bgcolor` property represents the background color of the table.

The `bgColor` attribute is deprecated in HTML 4.01. The CSS [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) property should be used instead by modifying the element's [`style`](https://developer.mozilla.org/en-US/docs/DOM/style#DOM_Style_Object) object or using a style rule.

Also available on DOM [`tbody`](tbodies), [`row`](rows) and [`cell`](https://developer.mozilla.org/en-US/docs/DOM/table.cells) objects.

Syntax
------

    color = table.bgColor
    table.bgColor = color

### Parameters

-   `color` is a string representing a color value.

Example
-------

    // Set table background color to lightblue
    var t = document.getElementById('TableA');
    t.bgColor = 'lightblue';

Specifications
--------------

-   [DOM Level 2 HTML:*HTMLTableElement* .bgColor](https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-83532985)

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

`bgColor`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/bgColor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/bgColor</a>
