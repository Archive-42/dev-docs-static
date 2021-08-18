# Document.scrollingElement

The `scrollingElement` read-only property of the [`Document`](../document) interface returns a reference to the [`Element`](../element) that scrolls the document. In standards mode, this is the root element of the document, [`document.documentElement`](documentelement).

When in quirks mode, the `scrollingElement` attribute returns the HTML `body` element if it exists and is [potentially scrollable](https://drafts.csswg.org/cssom-view/#potentially-scrollable), otherwise it returns null.

## Syntax

    var element = document.scrollingElement;

## Example

    var scrollElm = document.scrollingElement;
    scrollElm.scrollTop = 0;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-document-scrollingelement">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'scrollingElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scrollingElement`

44

12

48

No

31

9

44

44

48

32

9

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/scrollingElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/scrollingElement</a>
