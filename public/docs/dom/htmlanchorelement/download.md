# HTMLAnchorElement.download

The `HTMLAnchorElement.download` property is a [`DOMString`](../domstring) indicating that the linked resource is intended to be downloaded rather than displayed in the browser. The value, if any, specifies the default file name for use in labeling the resource in a local file system. If the name is not a valid file name in the underlying OS, the browser will adjust it.

**Note**: This value might not be used for download. This value cannot be used to determine whether the download will occur.

## Syntax

    var dnload = anchorElt.download;
    anchorElt.download = dnload;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/links.html#attr-hyperlink-download">HTML Living Standard<br />
<span class="small">The definition of 'download' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`download`

15

13

20

No

15

10.1

≤37

18

20

14

10.3

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/download" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/download</a>
