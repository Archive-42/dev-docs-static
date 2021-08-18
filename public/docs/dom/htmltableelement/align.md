# HTMLTableElement.align

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLTableElement.align` property represents the alignment of the table.

## Syntax

    HTMLTableElement.align = alignment;
    var alignment = HTMLTableElement.align;

### Parameters

`alignment`  
[`DOMString`](../domstring) with one of the following values:

- left
- center
- right

## Example

    // Set the alignment of a table
    var t = document.getElementById('TableA');
    t.align = 'center';

## Specifications

- W3C DOM 2 HTML Specification [_HTMLTableElement_ .align](https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-23180977).

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

`align`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/align" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/align</a>
