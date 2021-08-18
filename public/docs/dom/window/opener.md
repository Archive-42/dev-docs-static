Window.opener
=============

The [`Window`](../window) interface's `opener` property returns a reference to the window that opened the window, either with [`open()`](open), or by navigating a link with a [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-target) attribute.

In other words, if window `A` opens window `B`, `B.opener` returns `A`.

Syntax
------

    const openerWindow = window.opener

### Value

A [`Window`](../window)-like object referring to the window that opened the current window (using [`window.open()`](open), or by a link with [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-target) attribute set). If this window was not opened by being linked to or created by another, returns [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null).

If the opener is not on the same origin as the current page, functionality of the opener object is limited. For example, variables and functions on the window object are not accessible. However, navigation of the opener window is possible, which means that the opened page can open an URL in the original tab or window. In some cases, this makes phishing attacks possible, where a trusted page that is opened in the original window is replaced by a phishing page by the newly opened page.

In the following cases, the browser does not populate `window.opener`, but leaves it [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null):

-   The opener can be omitted by specifying `rel`=noopener on a link, or passing `noopener` in the [`windowFeatures`](open) parameter.
-   Windows opened because of links with a [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-target) of `_blank` don't get an `opener`, unless explicitly requested with `rel`=opener.
-   Having a [`Cross-Origin-Opener-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy) header with a value of `same-origin` prevents setting `opener`. Since the new window is loaded in a different browsing context, it won't have a reference to the opening window.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-opener">HTML Living Standard<br />
<span class="small">The definition of 'window.opener' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`opener`

1

12

1

9

3

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/opener" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/opener</a>
