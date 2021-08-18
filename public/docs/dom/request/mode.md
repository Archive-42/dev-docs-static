# Request.mode

The `mode` read-only property of the [`Request`](../request) interface contains the mode of the request (e.g., `cors`, `no-cors`, `same-origin`, or `navigate`.) This is used to determine if cross-origin requests lead to valid responses, and which properties of the response are readable.

## Syntax

    var myMode = request.mode;

### Value

A `RequestMode` value.

The associated mode, available values of which are:

- `same-origin` — If a request is made to another origin with this mode set, the result is an error. You could use this to ensure that a request is always being made to your origin.
- `no-cors` — Prevents the method from being anything other than `HEAD`, `GET` or `POST`, and the headers from being anything other than [simple headers](https://fetch.spec.whatwg.org/#simple-header). If any ServiceWorkers intercept these requests, they may not add or override any headers except for those that are [simple headers](https://fetch.spec.whatwg.org/#simple-header). In addition, JavaScript may not access any properties of the resulting [`Response`](../response). This ensures that ServiceWorkers do not affect the semantics of the Web and prevents security and privacy issues arising from leaking data across domains.
- `cors` — Allows cross-origin requests, for example to access various APIs offered by 3rd party vendors. These are expected to adhere to the [CORS protocol](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS). Only a [limited set](https://fetch.spec.whatwg.org/#concept-filtered-response-cors) of headers are exposed in the [`Response`](../response), but the body is readable.
- `navigate` — A mode for supporting navigation. The `navigate` value is intended to be used only by HTML navigation. A navigate request is created only while navigating between documents.

#### Default mode

Requests can be initiated in a variety of ways, and the mode for a request depends on the particular means by which it was initiated.

For example, when a `Request` object is created using the [`Request.Request`](request) constructor, the value of the `mode` property for that `Request` is set to `cors`.

However, for requests created other than by the [`Request.Request`](request) constructor, `no-cors` is typically used as the mode; for example, for embedded resources where the request is initiated from markup, unless the `crossorigin` attribute is present, the request is in most cases made using the `no-cors` mode — that is, for the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) or [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements (except when used with modules), or [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img), [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio), [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), or [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) elements.

## Example

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the request mode in a variable:

    var myRequest = new Request('flowers.jpg');
    var myMode = myRequest.mode; // returns "cors" by default

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-mode">Fetch<br />
<span class="small">The definition of 'mode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`mode`

42

14

39

No

29

10.1

49

49

39

No

10.3

5.0

`navigate_mode`

49

≤18

46

No

?

10.1

No

49

No

No

10.3

5.0

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/mode</a>
