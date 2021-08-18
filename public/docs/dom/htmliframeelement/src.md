# HTMLIFrameElement.src

The ` HTMLIFrameElement``.src ` property reflects the HTML <span class="page-not-created">`referrerpolicy`</span> attribute of the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element defining which referrer is sent when fetching the resource.

## Syntax

    refStr = iframeElt.src;
    iframeElt.src= refStr;

## Example

    var iframe = document.createElement("iframe");
    iframe.src = "/";
    var body = document.getElementsByTagName("body")[0];
    body.appendChild(iframe); // Fetch the image using the complete URL as the referrer

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-iframe-src">HTML Living Standard<br />
<span class="small">The definition of 'HTMLIFrameElement: src' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`src`

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

## See also

- <span class="page-not-created">`HTMLAnchorElement.src`</span>
- <span class="page-not-created">`HTMLAreaElement.src`</span>
- <span class="page-not-created">`HTMLAreaElement.src`</span>.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/src</a>
