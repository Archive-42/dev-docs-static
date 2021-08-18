# HTMLIFrameElement.contentWindow

The `contentWindow` property returns the [Window](../window) object of an [HTMLIFrameElement](../htmliframeelement). You can use this `Window` object to access the iframe's document and its internal DOM. This attribute is read-only, but its properties can be manipulated like the global `Window` object.

## Example of contentWindow

    var x = document.getElementsByTagName("iframe")[0].contentWindow;
    //x = window.frames[0];

    x.document.getElementsByTagName("body")[0].style.backgroundColor = "blue";
    // this would turn the 1st iframe in document blue.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-iframe-contentwindow">HTML Living Standard<br />
<span class="small">The definition of 'HTMLIFrameElement: contentWindow' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`contentWindow`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentWindow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentWindow</a>
