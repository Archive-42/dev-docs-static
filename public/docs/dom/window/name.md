Window.name
===========

The `Window.name` property gets/sets the name of the window's browsing context.

Syntax
------

    string = window.name;
    window.name = string;

Description
-----------

The name of the window is used primarily for setting targets for hyperlinks and forms. Browsing contexts do not need to have names.

Modern browsers will reset `Window.name` to an empty string if a tab loads a page from a different domain, and restore the name if the original page is reloaded (e.g. by selecting the "back" button). This prevents an untrusted page from accessing any information that the previous page might have stored in the property (potentially the new page might also modify such data, which might then be read by the original page if it was reloaded).

`Window.name` has also been used in some frameworks for providing cross-domain messaging (e.g. Dojo's [dojox.io.windowName](https://www.sitepen.com/blog/2008/07/22/windowname-transport/)) as a more secure alternative to JSONP. Modern web applications hosting sensitive data should, however, not rely on `window.name` for cross-domain messaging — that is not its intended purpose and there are safer/better ways of sharing information between windows. `Window.postMessage()` is the recommended mechanism.

**Note**: `window.name` converts all stored values to their string representations using the `toString` method.

Examples
--------

    <script>
        // Open a tab with a specific browsing context name
        const otherTab = window.open("url1", "_blank");
        if (otherTab)
            otherTab.name = "other-tab";
    </script>
    <a href="url2" target="other-tab">This link will be opened in the other tab.</a>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-name">HTML Living Standard<br />
<span class="small">The definition of 'Window.name' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-name">HTML5<br />
<span class="small">The definition of 'Window.name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`name`

1

12

1

Before Firefox 86, if a new page from another domain is loaded into a tab, then `window.name` is not set to an empty string, which can allow some cross-site attacks. See [bug 1685089](https://bugzil.la/1685089) and [bug 444222](https://bugzil.la/444222).

4

≤12.1

1

1

18

4

Before Firefox 86, if a new page from another domain is loaded into a tab, then `window.name` is not set to an empty string, which can allow some cross-site attacks. See [bug 1685089](https://bugzil.la/1685089) and [bug 444222](https://bugzil.la/444222).

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/name</a>
