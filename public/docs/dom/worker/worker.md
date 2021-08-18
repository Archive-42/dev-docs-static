Worker()
========

The `Worker()` constructor creates a [`Worker`](../worker) object that executes the script at the specified URL. This script must obey the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy).

**Note**: that there is a disagreement among browser manufacturers about whether a data URI is of the same origin or not. Though Gecko 10.0 (Firefox 10.0 / Thunderbird 10.0 / SeaMonkey 2.7) and later accept data URIs, that's not the case in all other browsers.

Syntax
------

    var myWorker = new Worker(aURL, options);

### Parameters

*aURL*  
A [`USVString`](../usvstring) representing the URL of the script the worker will execute. It must obey the same-origin policy.

 *options* <span class="badge inline optional">Optional</span>   
An object containing option properties that can be set when creating the object instance. Available properties are as follows:

-   `type`: A [`DOMString`](../domstring) specifying the type of worker to create. The value can be `classic` or `module`. If not specified, the default used is `classic`.
-   `credentials`: A [`DOMString`](../domstring) specifying the type of credentials to use for the worker. The value can be `omit`, `same-origin`, or `include`. If not specified, or if type is `classic`, the default used is `omit` (no credentials required).
-   `name`: A [`DOMString`](../domstring) specifying an identifying name for the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) representing the scope of the worker, which is mainly useful for debugging purposes.

### Exceptions

-   A `SecurityError` is raised if the document is not allowed to start workers, e.g. if the URL has an invalid syntax or if the same-origin policy is violated.
-   A `NetworkError` is raised if the MIME type of the worker script is incorrect. It *should* always be `text/javascript` (for historical reasons [other JavaScript MIME types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#javascript_types) may be accepted).
-   A `SyntaxError` is raised if *aURL* cannot be parsed.

Examples
--------

The following code snippet shows creation of a [`Worker`](../worker) object using the `Worker()` constructor and subsequent usage of the object:

    var myWorker = new Worker('worker.js');

    first.onchange = function() {
      myWorker.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

For a full example, see our [Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-worker">HTML Living Standard<br />
<span class="small">The definition of 'Worker()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Worker`

4

12

3.5

10

10.6

4

4

18

4

11

5.1

1.0

`ecmascript_modules`

80

80

No

No

67

No

80

80

No

57

No

13.0

`mime_checks`

?

?

81

No

?

?

?

?

81

?

?

?

`name`

70

18

55

No

57

No

Supported in [Safari Technology Preview 64](https://webkit.org/blog/8406/release-notes-for-safari-technology-preview-64/)

No

70

55

49

No

Supported in [Safari Technology Preview 64](https://webkit.org/blog/8406/release-notes-for-safari-technology-preview-64/)

10.0

`type`

80

80

No

No

67

No

80

80

No

57

No

13.0

**Note**: A browser can be marked as providing full support for `Worker()` even though it does not support worker scripts written as modules. As of Mar 1, 2019, only [Chrome 80+](https://web.dev/module-workers/) supports this feature, while [Firefox has an open feature request](https://bugzilla.mozilla.org/show_bug.cgi?id=1247687). No other browsers are known to have support for production usage of worker scripts written as modules. Without that support, worker scripts written as modules and modules used by worker scripts have to be transpiled or otherwise converted to non-module code in order to run.

See also
--------

The [`Worker`](../worker) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker/Worker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worker/Worker</a>
