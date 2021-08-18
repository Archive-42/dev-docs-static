HTMLAreaElement.host
====================

The `HTMLAreaElement.host` property is a [`USVString`](../usvstring) containing the host, that is the *hostname*, and then, if the *port* of the URL is nonempty, a `':'`, and the *port* of the URL.

Syntax
------

    // Getter
    string = area.host;
    // Setter
    area.host = string;

Examples
--------

    const area = document.createElement("area");

    area.href = "https://developer.mozilla.org/en-US/HTMLAreaElement"
    area.host == "developer.mozilla.org"

    area.href = "https://developer.mozilla.org:443/en-US/HTMLAreaElement"
    area.host == "developer.mozilla.org"
    // The port number is not included because 443 is the scheme's default port

    area.href = "https://developer.mozilla.org:4097/en-US/HTMLAreaElement"
    area.host == "developer.mozilla.org:4097"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-host">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.host' in that specification.</span></a></td></tr></tbody></table>

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

`host`

1

12

1

5

In Internet Explorer 9, the host of an [`<a>`](https://developer.mozilla.org/docs/Web/HTML/Element/a) always include the port (e.g. `developer.mozilla.org:443`), even if there is no explicit port in the `href` attribute value.

15

1

1

18

4

14

1

1.0

See also
--------

-   The [`HTMLAreaElement`](../htmlareaelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/host" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/host</a>
