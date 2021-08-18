HTML in XMLHttpRequest
======================

The W3C [`XMLHttpRequest`](../xmlhttprequest) specification adds [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) parsing support to [`XMLHttpRequest`](../xmlhttprequest), which originally supported only [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) parsing. This feature allows Web apps to obtain an HTML resource as a parsed [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) using `XMLHttpRequest`.

To get an overview of how to use `XMLHttpRequest` in general, see [Using XMLHttpRequest](using_xmlhttprequest).

Limitations
-----------

To discourage the synchronous use of `XMLHttpRequest`, HTML support is not available in the synchronous mode. Also, HTML support is only available if the [`responseType`](responsetype) property has been set to `"document"`. This limitation avoids wasting time parsing HTML uselessly when legacy code uses `XMLHttpRequest` in the default mode to retrieve [`responseText`](responsetext) for `text/html` resources. Also, this limitation avoids problems with legacy code that assumes that [`responseXML`](responsexml) is `null` for HTTP error pages (which often have a `text/html` response body).

Usage
-----

Retrieving an HTML resource as a DOM using [`XMLHttpRequest`](../xmlhttprequest) works just like retrieving an XML resource as a DOM using `XMLHttpRequest`, except you can't use the synchronous mode and you have to explicitly request a document by assigning the string `"document"` to the [`responseType`](responsetype) property of the `XMLHttpRequest` object after calling [`open()`](open) but before calling [`send()`](send).

    var xhr = new XMLHttpRequest();
    xhr.onload = function() {
      console.log(this.responseXML.title);
    }
    xhr.open("GET", "file.html");
    xhr.responseType = "document";
    xhr.send();

Feature detection
-----------------

### Method 1

This method relies on the "force async" nature of the feature. When you try to set `responseType` of an `XMLHttpRequest` object after it is opened as "sync". This throws an error in the browsers that implement the feature and works on others.

    function HTMLinXHR() {
      if (!window.XMLHttpRequest)
        return false;
      var req = new window.XMLHttpRequest();
      req.open('GET', window.location.href, false);
      try {
        req.responseType = 'document';
      } catch(e) {
        return true;
      }
      return false;
    }

[View on JSFiddle](https://jsfiddle.net/HTcKP/1/)

This method is synchronous, does not rely on external assets though it may not be as reliable as method 2 described below since it does not check the actual feature but an indication of that feature.

### Method 2

There are two challenges to detecting exactly if a browser supports HTML parsing in [`XMLHttpRequest`](../xmlhttprequest). First, the detection result is obtained asynchronously, because HTML support is only available in the asynchronous mode. Second, you have to actually fetch a test document over HTTP, because testing with a `data:` URL would end up testing `data:` URL support at the same time.

Thus, to detect HTML support, a test HTML file is needed on the server. This test file is small and is not well-formed XML:

    <title>&amp;&<</title>

If the file is named `detect.html`, the following function can be used for detecting HTML parsing support:

    function detectHtmlInXhr(callback) {
      if (!window.XMLHttpRequest) {
        window.setTimeout(function() { callback(false); }, 0);
        return;
      }
      var done = false;
      var xhr = new window.XMLHttpRequest();
      xhr.onreadystatechange = function() {
        if (this.readyState == 4 && !done) {
          done = true;
          callback(!!(this.responseXML && this.responseXML.title && this.responseXML.title == "&&<"));
        }
      }
      xhr.onabort = xhr.onerror = function() {
        if (!done) {
          done = true;
          callback(false);
        }
      }
      try {
        xhr.open("GET", "detect.html");
        xhr.responseType = "document";
        xhr.send();
      } catch (e) {
        window.setTimeout(function() {
          if (!done) {
            done = true;
            callback(false);
          }
        }, 0);
      }
    }

The argument `callback` is a function that will be called asynchronously with `true` as the only argument if HTML parsing is supported and `false` as the only argument if HTML parsing is not supported.

[View on JSFiddle](https://jsfiddle.net/xfvXR/1/)

Character encoding
------------------

If the character encoding is declared in the HTTP [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) header, that character encoding is used. Failing that, if there is a byte order mark, the encoding indicated by the byte order mark is used. Failing that, if there is a [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element that declares the encoding within the first 1024 bytes of the file, that encoding is used. Otherwise, the file is decoded as UTF-8.

Handling HTML on older browsers
-------------------------------

`XMLHttpRequest` originally supported only XML parsing. HTML parsing support is a recent addition. For older browsers, you can even use the [`XMLHttpRequest.responseText`](responsetext) property in association with [regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) in order to get, for example, the source code of an HTML element given its ID:

    function getHTML (oXHR, sTargetId) {
      var  rOpen = new RegExp("<(?!\!)\\s*([^\\s>]+)[^>]*\\s+id\\=[\"\']" + sTargetId + "[\"\'][^>]*>" ,"i"),
           sSrc = oXHR.responseText, aExec = rOpen.exec(sSrc);

      return aExec ? (new RegExp("(?:(?:.(?!<\\s*" + aExec[1] + "[^>]*[>]))*.?<\\s*" + aExec[1] + "[^>]*[>](?:.(?!<\\s*\/\\s*" + aExec[1] + "\\s*>))*.?<\\s*\/\\s*" + aExec[1] + "\\s*>)*(?:.(?!<\\s*\/\\s*" + aExec[1] + "\\s*>))*.?", "i")).exec(sSrc.slice(sSrc.indexOf(aExec[0]) + aExec[0].length)) || "" : "";
    }

    var oReq = new XMLHttpRequest();
    oReq.open("GET", "yourPage.html", true);
    oReq.onload = function () { console.log(getHTML(this, "intro")); };
    oReq.send(null);

**Note:** This solution is very expensive for the interpreter. **Use it only when it is really necessary**.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTML_in_XMLHttpRequest`

1

12

1

7

5

Implemented via `ActiveXObject('Microsoft.XMLHTTP')`

8

1.2

1

18

4

10.1

1

1.0

`XMLHttpRequest`

1

12

1

7

≤12.1

3

1

18

4

≤12.1

1

1.0

`abort`

18

12

Yes

5

Yes

1.2

≤37

Yes

Yes

Yes

Yes

Yes

`abort_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`error_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

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

`load_event`

Yes

≤79

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`loadend_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`loadstart_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`onreadystatechange`

1

12

1

5

9

1.2

1

18

4

10.1

1

1.0

`open`

1

12

1

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

5

8

1.2

1

18

4

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

10.1

1

1.0

`overrideMimeType`

1

12

Yes

11

5

Implemented via `ActiveXObject`

Yes

1.2

1

18

Yes

Yes

Yes

1.0

`progress_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`readyState`

1

12

1

7

8

1.2

1

18

4

10.1

1

1.0

`response`

9

12

6

10

11.6

5.1

≤37

18

6

12

6

1.0

`responseText`

1

12

1

5

Before Internet Explorer 10, the value of `XMLHttpRequest.responseText` could be read only once the request was complete.

8

1.2

1

18

4

10.1

1

1.0

`responseType`

31

12

6

10

12-15

18

7

55

55

50

42

7

6.0

`responseURL`

37

14

32

No

24

8

37

37

32

24

Yes

3.0

`responseXML`

Yes

12

Yes

Prior to Firefox 51, an error parsing the received data added a `<parsererror>` node to the top of the `Document` and then returned the `Document` in whatever state it happens to be in. This was inconsistent with the specification. Starting with Firefox 51, this scenario now correctly returns `null` as per the spec.

Yes

Yes

Yes

Yes

Yes

Yes

Prior to Firefox 51, an error parsing the received data added a `<parsererror>` node to the top of the `Document` and then returned the `Document` in whatever state it happens to be in. This was inconsistent with the specification. Starting with Firefox 51, this scenario now correctly returns `null` as per the spec.

Yes

Yes

Yes

`send`

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

`status`

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

8

1.2

1

18

4

10.1

1

1.0

`statusText`

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

Yes

1.2

1

18

4

Yes

Yes

1.0

`timeout`

29

12

12

8

17

12-16

6.1

≤37

29

14

18

12-16

7

2.0

`timeout_event`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`upload`

1

12

Yes

10

Yes

10

1

18

Yes

Yes

Yes

1.0

`withCredentials`

3

12

3.5

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

10

Internet Explorer versions 8 and 9 supported cross-domain requests (CORS) using [`XDomainRequest`](https://developer.mozilla.org/docs/Web/API/XDomainRequest).

12

4

≤37

18

4

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

12

3.2

1.0

`worker_support`

4

Not supported in service workers.

12

Not supported in service workers.

3.5

Not supported in service workers.

10

Not supported in service workers.

10.6

Not supported in service workers.

4

Not supported in service workers.

4

Not supported in service workers.

18

Not supported in service workers.

4

Not supported in service workers.

11

Not supported in service workers.

5.1

Not supported in service workers.

1.0

Not supported in service workers.

BCD tables only load in the browser

See also
--------

-   [`XMLHttpRequest`](../xmlhttprequest)
-   [Using XMLHttpRequest](using_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/HTML_in_XMLHttpRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/HTML_in_XMLHttpRequest</a>
