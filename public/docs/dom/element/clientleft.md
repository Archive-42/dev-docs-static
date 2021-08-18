Element.clientLeft
==================

The width of the left border of an element in pixels. It includes the width of the vertical scrollbar if the text direction of the element is right–to–left and if there is an overflow causing a left vertical scrollbar to be rendered. `clientLeft` does not include the left margin or the left padding. `clientLeft` is read-only.

When [`layout.scrollbar.side` preference](http://kb.mozillazine.org/Layout.scrollbar.side) is set to 1 or to 3 and when the text-direction is set to RTL, **then the vertical scrollbar is positioned on the left** and this impacts the way clientLeft is computed.

**Note:** This property will round the value to an integer. If you need a fractional value, use [`element.getBoundingClientRect()`](getboundingclientrect).

**Note:** When an element has `display: inline`, `clientLeft` returns `0` regardless of the element's border.

Syntax
------

    var left = element.clientLeft;

Example
-------

padding-top

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

padding-bottom

**Left** **Top** **Right** **Bottom** *margin-top* *margin-bottom* *border-top* *border-bottom*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-clientleft">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'clientLeft' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`clientLeft`

1

12

1

5

8

3

1

18

4

10.1

1

1.0

Notes
-----

`clientLeft` was first introduced in the MS IE DHTML object model.

The position of the vertical scrollbar in right–to–left text direction set on the element will depend on the [`layout.scrollbar.side` preference](http://kb.mozillazine.org/Layout.scrollbar.side)

[Gecko](https://developer.mozilla.org/en-US/Gecko)-based applications support `clientLeft` starting with Gecko 1.9 ([Firefox 3](https://developer.mozilla.org/en-US/Firefox_3), implemented in [bug 111207](https://bugzilla.mozilla.org/show_bug.cgi?id=111207)). This property is not supported in Firefox 2 and earlier.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/clientLeft" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/clientLeft</a>
