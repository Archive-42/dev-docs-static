Network Error Logging
=====================

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

Network Error Logging is a mechanism that can be configured via the [`NEL`](headers/nel) HTTP *[response header](https://developer.mozilla.org/en-US/docs/Glossary/Response_header)*. This experimental header allows web sites and applications to opt-in to receive reports about failed (and, if desired, successful) network fetches from supporting browsers.

Reports are sent to a reporting group defined within a [`Report-To`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Report-To) header.

Usage
-----

Web applications opt in to this behaviour with the NEL header, which is a *[JSON-encoded](https://developer.mozilla.org/en-US/docs/Glossary/Response_header)* object:

    NEL: { "report_to": "nel", 
           "max_age": 31556952 }

An origin considered secure by the browser is required.

The following object keys can be specified in the NEL header:

report\_to  
The [reporting API](https://developer.mozilla.org/en-US/docs/Web/API/Reporting_API) group to send network error reports to (see below).

max\_age  
Specifies the lifetime of the policy, in seconds (in a similar way to e.g. HSTS policies are time-restricted). The referenced reporting group should have a lifetime at least as long as the NEL policy.

include\_subdomains  
If true, the policy applies to all subdomains under the origin that the policy header is set. The reporting group should also be set to include subdomains, if this option is to be enabled.

success\_fraction  
Floating point value between 0 and 1 which specifies the proportion of **successful** network requests to report. Defaults to 0, so that no successful network requests will be reported if the key is not present in the JSON payload.

failure\_fraction  
Floating point value between 0 and 1 which specifies the proportion of **failed** network requests to report. Defaults to 1, so that all failed network requests will be reported if the key is not present in the JSON payload.

The reporting group referenced above is defined in the usual manner within the [`Report-To`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Report-To) header, for example:

    Report-To: { "group": "nel",
                 "max_age": 31556952,
                 "endpoints": [
                   { "url": "https://example.com/csp-reports" }
                 ] }

Error reports
-------------

In these examples, the entire reporting API payload is shown. The top-level `"body"` key contains the network error report.

### HTTP 400 (Bad Request) response

    {
      "age": 20,
      "type": "network-error",
      "url": "https://example.com/previous-page",
      "body": {
        "elapsed_time": 338,
        "method": "POST",
        "phase": "application",
        "protocol": "http/1.1",
        "referrer": "https://example.com/previous-page",
        "sampling_fraction": 1,
        "server_ip": "137.205.28.66",
        "status_code": 400,
        "type": "http.error",
        "url": "https://example.com/bad-request"
      }
    }

### DNS name not resolved

Note that the phase is set to `dns` in this report and no `server_ip` is available to include.

    {
      "age": 20,
      "type": "network-error",
      "url": "https://example.com/previous-page",
      "body": {
        "elapsed_time": 18,
        "method": "POST",
        "phase": "dns",
        "protocol": "http/1.1",
        "referrer": "https://example.com/previous-page",
        "sampling_fraction": 1,
        "server_ip": "",
        "status_code": 0,
        "type": "dns.name_not_resolved",
        "url": "https://example-host.com/"
      }
    }

The type of the network error may be one of the following pre-defined values from the specification, but browsers can add and send their own error types:

`dns.unreachable`  
The user's DNS server is unreachable

`dns.name_not_resolved`  
The user's DNS server responded but was unable to resolve an IP address for the requested URI.

`dns.failed`  
Request to the DNS server failed due to reasons not covered by previous errors (e.g. SERVFAIL)

`dns.address_changed`  
For security reasons, if the server IP address that delivered the original report is different to the current server IP address at time of error generation, the report data will be downgraded to only include information about this problem and the type set to `dns.address_changed`.

`tcp.timed_out`  
TCP connection to the server timed out

`tcp.closed`  
The TCP connection was closed by the server

`tcp.reset`  
The TCP connection was reset

`tcp.refused`  
The TCP connection was refused by the server

`tcp.aborted`  
The TCP connection was aborted

`tcp.address_invalid`  
The IP address is invalid

`tcp.address_unreachable`  
The IP address is unreachable

`tcp.failed`  
The TCP connection failed due to reasons not covered by previous errors

`http.error`  
The user agent successfully received a response, but it had a [4xx](https://tools.ietf.org/html/rfc7231#section-6.5) or [5xx](https://tools.ietf.org/html/rfc7231#section-6.6) status code

`http.protocol.error`  
The connection was aborted due to an HTTP protocol error

`http.response.invalid`  
Response is empty, has a content-length mismatch, has improper encoding, and/or other conditions that prevent user agent from processing the response

`http.response.redirect_loop`  
The request was aborted due to a detected redirect loop

`http.failed`  
The connection failed due to errors in HTTP protocol not covered by previous errors

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/network-error-logging/#introduction">Network Error Logging</a></td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

[`NEL`](headers/nel)

71

71

69

Disabled

Disabled From version 69: this feature is behind the `Reporting` runtime flag (needs to be set to `true`).

79

No

No

58

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

[`NEL`](headers/nel)

71

71

No

50

No

10.2

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Network_Error_Logging$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Network_Error_Logging" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Network_Error_Logging</a>
