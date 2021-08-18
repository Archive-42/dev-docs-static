# Location: hostname

The `hostname` property of the [`Location`](../location) interface is a [`USVString`](../usvstring) containing the domain of the URL.

## Syntax

    string = object.hostname;
    object.hostname = string;

## Examples

    // Let's an <a id="myAnchor" href="/en-US/docs/Location.hostname"> element be in the document
    var anchor = document.getElementById("myAnchor");
    var result = anchor.hostname; // Returns:'developer.mozilla.org'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-hostname">HTML Living Standard<br />
<span class="small">The definition of 'hostname' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`hostname`

1

12

1

3

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/hostname" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/hostname</a>
