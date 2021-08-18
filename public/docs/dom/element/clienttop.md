# Element.clientTop

The width of the top border of an element in pixels. It is a read-only, integer property of element.

As it happens, all that lies between the two locations (`offsetTop` and client area top) is the element's border. This is because the `offsetTop` indicates the location of the top of the border (not the margin) while the client area starts immediately below the border, (client area includes padding.) Therefore, the **clientTop** value will always equal the integer portion of the `.getComputedStyle()` value for "border-top-width". (Actually might be Math.round(parseFloat()).) For example, if the computed "border-top-width" is zero, then `clientTop` is also zero.

**Note:** This property will round the value to an integer. If you need a fractional value, use [`element.getBoundingClientRect()`](getboundingclientrect).

[Gecko](https://developer.mozilla.org/en-US/Gecko)-based applications support `clientTop` starting with Gecko 1.9 ([Firefox 3](https://developer.mozilla.org/en-US/Firefox_3), implemented in [bug 111207](https://bugzilla.mozilla.org/show_bug.cgi?id=111207)). This property is not supported in Firefox 2 and earlier.

## Syntax

    var top = element.clientTop;

## Example

In the following illustration, the client area is show in white. (The segments labeled "Top", "Right", etc. have no significance regarding the client area.) The clientTop value is the distance from where the margin (yellow) area ends and the padding and content areas (white) begin.

padding-top

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

padding-bottom

**Left** **Top** **Right** **Bottom** _margin-top_ _margin-bottom_ _border-top_ _border-bottom_

## Notes

`clientTop` was first introduced in the MS IE DHTML object model.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-clienttop">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'clientTop' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`clientTop`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/clientTop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/clientTop</a>
