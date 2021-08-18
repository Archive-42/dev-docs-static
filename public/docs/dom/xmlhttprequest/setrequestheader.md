XMLHttpRequest.setRequestHeader()
=================================

The [`XMLHttpRequest`](../xmlhttprequest) method `setRequestHeader()` sets the value of an HTTP request header. When using `setRequestHeader()`, you must call it after calling [`open()`](open), but before calling [`send()`](send). If this method is called several times with the same header, the values are merged into one single request header.

Each time you call `setRequestHeader()` after the first time you call it, the specified text is appended to the end of the existing header's content.

If no [`Accept`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept) header has been set using this, an `Accept` header with the type `"*/*"` is sent with the request when [`send()`](send) is called.

For security reasons, some headers can only be controlled by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

**Note:** For your custom fields, you may encounter a "**not allowed by Access-Control-Allow-Headers in preflight response**" exception when you send requests across domains. In this situation, you need to set up the [`Access-Control-Allow-Headers`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Headers) in your response header at server side.

Syntax
------

    XMLHttpRequest.setRequestHeader(header, value)

### Parameters

`header`  
The name of the header whose value is to be set.

`value`  
The value to set as the body of the header.

### Return value

`undefined`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-setrequestheader()-method">XMLHttpRequest<br />
<span class="small">The definition of 'setRequestHeader()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`setRequestHeader`

1

12

1

5

8

1.2

1

18

4

10.1

1

1.0

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   [HTML in XMLHttpRequest](html_in_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/setRequestHeader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/setRequestHeader</a>
