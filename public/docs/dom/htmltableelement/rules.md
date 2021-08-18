# HTMLTableElement.rules

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLTableElement.rules` property indicates which cell borders to render in the table.

## Syntax

    HTMLTableElement.rules = rules;
    var rules = HTMLTableElement.rules;

### Parameters

`rules` is a string with one of the following values:

`none`  
No rules

`groups`  
Lines between groups only

`rows`  
Lines between rows

`cols`  
Lines between cols

`all`  
Lines between all cells

## Example

    // Turn on all the internal borders of a table
    var t = document.getElementById("TableID");
    t.rules = "all";

## Specifications

- W3C DOM 2 HTML Specification

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

`rules`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/rules" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/rules</a>
