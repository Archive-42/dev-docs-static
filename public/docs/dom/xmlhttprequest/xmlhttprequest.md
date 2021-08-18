XMLHttpRequest()
================

**Draft**

This page is not complete.

The `XMLHttpRequest()` constructor creates a new [`XMLHttpRequest`](../xmlhttprequest).

For details about how to use `XMLHttpRequest`, see <a href="using_xmlhttprequest" class="internal">Using XMLHttpRequest</a>.

Syntax
------

    const request = new XMLHttpRequest();

### Parameters

None.

### Return value

A new [`XMLHttpRequest`](../xmlhttprequest) object. The object must be prepared by at least calling [`open()`](open) to initialize it before calling [`send()`](send) to send the request to the server.

Non-standard Firefox syntax
---------------------------

Firefox 16 added a non-standard parameter to the constructor that can enable anonymous mode (see [bug 692677](https://bugzilla.mozilla.org/show_bug.cgi?id=692677)). Setting the `mozAnon` flag to `true` effectively resembles the [`AnonXMLHttpRequest()`](https://www.w3.org/TR/2012/WD-XMLHttpRequest-20120117/#dom-anonxmlhttprequest) constructor described in older versions of the XMLHttpRequest specification.

    const request = new XMLHttpRequest(paramsDictionary);

### Parameters (non-standard)

 `objParameters`   
There are two flags you can set:

`mozAnon`  
Boolean: Setting this flag to `true` will cause the browser not to expose the [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) and [user credentials](https://www.w3.org/TR/2012/WD-XMLHttpRequest-20120117/#user-credentials) when fetching resources. Most important, this means that [cookies](https://developer.mozilla.org/en-US/docs/Glossary/Cookie) will not be sent unless explicitly added using setRequestHeader.

`mozSystem`  
Boolean: Setting this flag to `true` allows making cross-site connections without requiring the server to opt-in using [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS). *Requires setting `mozAnon: true`, i.e. this can't be combined with sending cookies or other user credentials. This only works in privileged (reviewed) apps ([bug 692677](https://bugzilla.mozilla.org/show_bug.cgi?id=692677)); it does not work on arbitrary webpages loaded in Firefox*

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   [HTML in XMLHttpRequest](html_in_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/XMLHttpRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/XMLHttpRequest</a>
