# Document.getBoxObjectFor()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns a `boxObject` (x, y, width, height) for a specified element.

**Note:** This method is obsolete. You should use the [`element.getBoundingClientRect()`](../element/getboundingclientrect) method instead.

## Syntax

    boxObject = document.getBoxObjectFor(element);

- boxObject is an <span class="page-not-created">`nsIBoxObject`</span>.
- element is a [`DOMElement`](../element).

## Example

    var myDiv = document.getElementById("myDiv"),
        boxObj = document.getBoxObjectFor (myDiv);

    alert (
      "x:" + boxObj.x +
      ", y:" + boxObj.y +
      ", Width:" + boxObj.width +
      ", Height:" + boxObj.height
    );

## Notes

Specified in [nsIXULDocument.idl](http://mxr.mozilla.org/mozilla-central/source/dom/interfaces/xul/nsIDOMXULDocument.idl)

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

`getBoxObjectFor`

No

No

1-3.6

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getBoxObjectFor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getBoxObjectFor</a>
