XMLHttpRequest.getResponseHeader()
==================================

The [`XMLHttpRequest`](../xmlhttprequest) method `getResponseHeader()` returns the string containing the text of a particular header's value. If there are multiple response headers with the same name, then their values are returned as a single concatenated string, where each value is separated from the previous one by a pair of comma and space. The `getResponseHeader()` method returns the value as a UTF byte sequence.

**Note:** The search for the header name is case-insensitive.

If you need to get the raw string of all of the headers, use the [`getAllResponseHeaders()`](getallresponseheaders) method, which returns the entire raw header string.

Syntax
------

    var myHeader = XMLHttpRequest.getResponseHeader(headerName);

### Parameters

headerName  
A [`ByteString`](../bytestring) indicating the name of the header you want to return the text value of.

### Return value

A [`ByteString`](../bytestring) representing the header's text value, or `null` if either the response has not yet been received or the header doesn't exist in the response.

Example
-------

In this example, a request is created and sent, and a `readystatechange` handler is established to look for the [`readyState`](readystate) to indicate that the headers have been received; when that is the case, the value of the [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) header is fetched. If the `Content-Type` isn't the desired value, the [`XMLHttpRequest`](../xmlhttprequest) is canceled by calling [`abort()`](abort).

    var client = new XMLHttpRequest();
    client.open("GET", "unicorns-are-teh-awesome.txt", true);
    client.send();

    client.onreadystatechange = function() {
      if(this.readyState == this.HEADERS_RECEIVED) {
        var contentType = client.getResponseHeader("Content-Type");
        if (contentType != my_expected_type) {
          client.abort();
        }
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#dom-xmlhttprequest-getresponseheader">XMLHttpRequest<br />
<span class="small">The definition of 'getResponseHeader()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`getResponseHeader`

1

12

1

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

5

8

1.2

1

18

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

10.1

1

1.0

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   [HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
-   [`getAllResponseHeaders()`](getallresponseheaders)
-   [`response`](response)
-   Setting request headers: [`setRequestHeader()`](setrequestheader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getResponseHeader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getResponseHeader</a>
