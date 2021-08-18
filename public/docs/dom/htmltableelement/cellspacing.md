HTMLTableElement.cellSpacing
============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

While you should instead use the CSS [`border-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing) property, the obsolete [`HTMLTableElement`](../htmltableelement) interface's `cellSpacing` property represents the spacing around the individual [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th) and [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) elements representing a table's cells. Any two cells are separated by the sum of the `cellSpacing` of each of the two cells.

Syntax
------

    HTMLTableElement.cellSpacing = spacing;
    var spacing = HTMLTableElement.cellSpacing;

### Value

A [`DOMString`](../domstring) which is either a number of pixels (such as `"10"`) or a percentage value (like `"10%"`).

Example
-------

This example sets cell spacing for a given table to 10 pixels.

    var t = document.getElementById('TableA');
    t.cellSpacing = "10";

Specifications
--------------

-   W3C DOM 2 HTML Specification [*HTMLTableElement* .cellSpacing](https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-68907883).

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

`cellSpacing`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/cellSpacing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/cellSpacing</a>
