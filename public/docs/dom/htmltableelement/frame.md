HTMLTableElement.frame
======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`HTMLTableElement`](../htmltableelement) interface's `frame` property is a string that indicates which of the table's exterior borders should be drawn.

Syntax
------

    HTMLTableElement.frame = frameSides;
    var frameSides = HTMLTableElement.frame;

### Parameters

`frameSides` is a string whose value is one of the following values:

`void`  
No sides. This is the default.

`"above"`  
Top side

`"below"`  
Bottom side

`"hsides"`  
Top and bottom only

`"vsides"`  
Right and left sides only

`"lhs"`  
Left-hand side only

`"rhs"`  
Right-hand side only

`"box"`  
All four sides

`"border"`  
All four sides

Example
-------

    // Set the frame of TableA to 'border'
    var t = document.getElementById('TableA');
    t.frame  = "border";
    t.border = "2px";

Specifications
--------------

-   W3C DOM 2 HTML Specification

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

`frame`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/frame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/frame</a>
