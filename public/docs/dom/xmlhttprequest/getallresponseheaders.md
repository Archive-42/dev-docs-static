XMLHttpRequest.getAllResponseHeaders()
======================================

The [`XMLHttpRequest`](../xmlhttprequest) method `getAllResponseHeaders()` returns all the response headers, separated by [CRLF](https://developer.mozilla.org/en-US/docs/Glossary/CRLF), as a string, or returns `null` if no response has been received. If a network error happened, an empty string is returned.

**Note:** For multipart requests, this returns the headers from the *current* part of the request, not from the original channel.

Syntax
------

    var headers = XMLHttpRequest.getAllResponseHeaders();

### Parameters

None.

### Return value

A [`ByteString`](../bytestring) representing all of the response's headers (except those whose field name is `Set-Cookie` or `Set-Cookie2`) separated by [CRLF](https://developer.mozilla.org/en-US/docs/Glossary/CRLF), or `null` if no response has been received. If a network error happened, an empty string is returned.

An example of what a raw header string looks like:

    date: Fri, 08 Dec 2017 21:04:30 GMT\r\n
    content-encoding: gzip\r\n
    x-content-type-options: nosniff\r\n
    server: meinheld/0.6.1\r\n
    x-frame-options: DENY\r\n
    content-type: text/html; charset=utf-8\r\n
    connection: keep-alive\r\n
    strict-transport-security: max-age=63072000\r\n
    vary: Cookie, Accept-Encoding\r\n
    content-length: 6502\r\n
    x-xss-protection: 1; mode=block\r\n

Each line is terminated by both carriage return and line feed characters (`\r\n`). These are essentially delimiters separating each of the headers.

**Note**: In modern browsers, the header names are returned in all lower case, as per the latest spec.

Example
-------

This example examines the headers in the request's `readystatechange` event handler, [`XMLHttpRequest.onreadystatechange`](onreadystatechange). The code shows how to obtain the raw header string, as well as how to convert it into an array of individual headers and then how to take that array and create a mapping of header names to their values.

    var request = new XMLHttpRequest();
    request.open("GET", "foo.txt", true);
    request.send();

    request.onreadystatechange = function() {
      if(this.readyState == this.HEADERS_RECEIVED) {

        // Get the raw header string
        var headers = request.getAllResponseHeaders();

        // Convert the header string into an array
        // of individual headers
        var arr = headers.trim().split(/[\r\n]+/);

        // Create a map of header names to values
        var headerMap = {};
        arr.forEach(function (line) {
          var parts = line.split(': ');
          var header = parts.shift();
          var value = parts.join(': ');
          headerMap[header] = value;
        });
      }
    }

Once this is done, you can, for example:

    var contentType = headerMap["content-type"];

This obtains the value of the [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) header into the variable `contentType`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-getallresponseheaders()-method">XMLHttpRequest<br />
<span class="small">The definition of 'getAllResponseHeaders()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`getAllResponseHeaders`

1

12

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

5

Yes

1.2

1

Yes

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

Yes

Yes

Yes

`lowercase`

Yes

79

64

No

Yes

Yes

Yes

Yes

64

Yes

Yes

Yes

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   Setting request headers: [`setRequestHeader()`](setrequestheader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getAllResponseHeaders" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getAllResponseHeaders</a>
