HTMLAreaElement.search
======================

The `HTMLAreaElement.search` property is a search string, also called a *query string*, that is [`USVString`](../usvstring) containing a `'?'` followed by the parameters of the URL.

Modern browsers provide `URLSearchParams` and `URL.searchParams` to make it easy to parse out the parameters from the querystring.

Syntax
------

    // Getter
    string = area.search;
    // Setter
    area.search = string;

Examples
--------

### Getting the search string from an area link

    // An <area id="myArea" href="/en-US/docs/HTMLAreaElement?q=123"> element is in the document
    const area = document.getElementById("myArea");
    area.search; // returns '?q=123'

### Advanced parsing using URLSearchParams

Alternatively, [`URLSearchParams`](../urlsearchparams/get#examples) can be used:

    let params = new URLSearchParams(queryString);
    let q = parseInt(params.get("q"); // returns the number 123

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-search">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.search' in that specification.</span></a></td></tr></tbody></table>

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

`search`

1

12

1

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

5

15

1

1

18

4

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

14

1

1.0

See also
--------

-   The [`HTMLAreaElement`](../htmlareaelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/search" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/search</a>
